<template>
  <div
    class="group bg-white rounded-2xl overflow-hidden flex flex-col h-full shadow-lg transition-all duration-500 border border-gray-100 hover:border-gray-200"
  >
    <!-- Image Container -->
    <div class="relative overflow-hidden h-48">
      <img
        :src="blog.image"
        :alt="blog.title"
        class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
      />
      <div
        class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"
      ></div>

      <!-- Category Badge -->
      <div class="absolute top-4 left-4">
        <span
          class="inline-flex items-center px-3 py-1.5 bg-white/90 backdrop-blur-sm text-gray-800 rounded-full text-xs font-semibold uppercase tracking-wide shadow-sm"
        >
          {{ blog.category }}
        </span>
      </div>

      <!-- Read Time -->
      <div class="absolute top-4 right-4">
        <div
          class="flex items-center gap-1 bg-black/70 text-white rounded-full px-3 py-1.5 text-xs font-medium backdrop-blur-sm"
        >
          <Icon name="heroicons:clock" class="w-3 h-3" />
          {{ blog.readTime }}
        </div>
      </div>
    </div>

    <!-- Content -->
    <div class="p-6 flex flex-col flex-grow">
      <!-- Title -->
      <h3
        class="text-xl font-bold text-gray-900 mb-3 line-clamp-2 group-hover:text-primary transition-colors duration-300"
      >
        {{ blog.title }}
      </h3>

      <!-- Excerpt -->
      <p
        class="text-gray-600 text-sm leading-relaxed mb-4 line-clamp-3 flex-grow"
      >
        {{ blog.excerpt }}
      </p>

      <!-- Tags -->
      <div class="flex flex-wrap gap-2 mb-4">
        <span
          v-for="tag in blog.tags"
          :key="tag"
          class="inline-flex items-center px-2.5 py-0.5 bg-primary/10 text-gray-700 rounded-full text-xs font-medium"
        >
          #{{ tag }}
        </span>
      </div>

      <!-- Footer -->
      <div
        class="flex items-center justify-between pt-4 border-t border-gray-100"
      >
        <div class="flex items-center space-x-3">
          <div class="relative">
            <img
              :src="blog.authorImage"
              :alt="blog.author"
              class="w-10 h-10 rounded-full object-cover ring-2 ring-white shadow-md"
            />
            <span
              class="absolute bottom-0 right-0 w-3 h-3 bg-green-400 rounded-full border-2 border-white"
            ></span>
          </div>
          <div class="flex flex-col">
            <span class="text-sm font-semibold text-gray-800">{{
              blog.author
            }}</span>
            <span class="text-xs text-gray-500">{{
              formatRelativeDate(blog.publishDate)
            }}</span>
          </div>
        </div>

        <a
          :href="blog.link"
          class="w-10 h-10 bg-gradient-to-r from-primary to-secondary text-white rounded-full flex items-center justify-center hover:shadow-lg transition-all duration-300 group-hover:scale-110"
        >
          <Icon name="heroicons:arrow-right" class="w-4 h-4" />
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  blog: {
    type: Object,
    required: true,
  },
});

// Helper functions
const formatMonth = (date) => {
  return new Date(date).toLocaleString("default", { month: "short" });
};

const formatDay = (date) => {
  return new Date(date).getDate();
};

const formatYear = (date) => {
  return new Date(date).getFullYear();
};

const formatRelativeDate = (date) => {
  const now = new Date();
  const publishDate = new Date(date);
  const diffTime = Math.abs(now - publishDate);
  const diffDays = Math.ceil(diffTime / (1000 * 60 * 60 * 24));

  if (diffDays === 1) return "Today";
  if (diffDays === 2) return "Yesterday";
  if (diffDays < 7) return `${diffDays - 1} days ago`;
  if (diffDays < 30) return `${Math.floor(diffDays / 7)} weeks ago`;
  return `${Math.floor(diffDays / 30)} months ago`;
};
</script>

<style scoped></style>
