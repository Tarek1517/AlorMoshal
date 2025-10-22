<script setup>
const props = defineProps({
  course: {
    type: Object,
    required: true,
  },
});
</script>

<template>
  <NuxtLink :to="`/courses/${course.id}`" class="block group">
    <div
      class="bg-white rounded-xl shadow-lg overflow-hidden transition-all duration-500 hover:shadow-2xl border-0 h-full flex flex-col hover:-translate-y-2 relative"
    >
      <!-- Premium Badge -->
      <div v-if="course.featured" class="absolute top-4 left-4 z-20">
        <div
          class="bg-gradient-to-r from-yellow-400 to-orange-500 text-white px-4 py-1.5 rounded-full text-xs font-bold shadow-lg flex items-center gap-1"
        >
          <Icon name="heroicons:star" class="w-3 h-3" />
          ফিচারড
        </div>
      </div>

      <!-- Favorite Button -->
      <div class="absolute top-4 right-4 z-20">
        <button
          class="p-2 bg-white/90 backdrop-blur-sm rounded-full shadow-lg hover:shadow-xl transition-all duration-300 hover:scale-110 hover:text-red-500 text-gray-600"
        >
          <Icon name="heroicons:heart" class="w-4 h-4" />
        </button>
      </div>

      <!-- Course Image -->
      <div class="relative h-48 overflow-hidden">
        <img
          :src="course.image"
          :alt="course.title"
          class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
          loading="lazy"
        />
        <div class="absolute inset-0 bg-gradient-to-t from-black/40 via-transparent to-transparent"></div>

        <!-- Level Badge -->
        <div class="absolute bottom-4 left-4">
          <span
            :class="[
              'px-3 py-1.5 text-xs font-bold text-white rounded-full shadow-lg backdrop-blur-sm',
              course.level === 'শুরুতি'
                ? 'bg-green-500'
                : course.level === 'মধ্যবর্তী'
                ? 'bg-yellow-500'
                : 'bg-red-500',
            ]"
          >
            {{ course.level }}
          </span>
        </div>

        <!-- Category Badge -->
        <div class="absolute bottom-4 right-4">
          <span
            class="px-3 py-1.5 bg-white/20 backdrop-blur-sm text-white text-xs font-semibold rounded-full border border-white/30"
          >
            {{ course.category }}
          </span>
        </div>
      </div>

      <!-- Content Section -->
      <div class="p-6 flex-1 flex flex-col">
        <!-- Course Title -->
        <h3
          class="text-xl font-bold text-gray-900 mb-3 line-clamp-2 group-hover:text-blue-600 transition-colors duration-300 leading-tight"
        >
          {{ course.title }}
        </h3>

        <!-- Instructor -->
        <div class="flex items-center gap-2 mb-4">
          <div
            class="w-8 h-8 bg-gradient-to-r from-primary to-secondary rounded-full flex items-center justify-center text-white text-xs font-bold"
          >
            {{
              course.instructor
                .split(" ")
                .map((n) => n[0])
                .join("")
            }}
          </div>
          <span class="text-sm text-gray-600 font-medium">{{
            course.instructor
          }}</span>
        </div>

        <!-- Rating and Students -->
        <div class="flex items-center justify-between mb-4">
          <div class="flex items-center gap-2">
            <div class="flex items-center gap-1">
              <Icon name="heroicons:star" class="w-4 h-4 text-yellow-400" />
              <span class="text-sm font-bold text-gray-900">{{ course.rating || 4.8 }}</span>
            </div>
            <span class="text-gray-400">•</span>
            <span class="text-sm text-gray-600">{{ course.students || "1.2k" }} শিক্ষার্থী</span>
          </div>
          <div
            class="text-sm font-semibold text-gray-900 bg-gray-100 px-3 py-1 rounded-full"
          >
            {{ course.duration }}
          </div>
        </div>

        <!-- Price and CTA -->
        <div
          class="mt-auto flex items-center justify-between pt-4 border-t border-gray-100"
        >
          <div class="flex items-baseline gap-1">
            <span class="text-2xl font-bold text-gray-900">{{ course.price }}</span>
            <span class="text-sm text-gray-500 line-through">৳999</span>
          </div>
          <button
            class="bg-secondary text-white px-6 py-2.5 rounded-xl font-semibold text-sm hover:shadow-lg transition-all duration-300 hover:scale-105 flex items-center gap-2 group-hover:gap-3"
          >
            এখন ভর্তি হোন
            <Icon
              name="heroicons:arrow-right"
              class="w-4 h-4 transition-transform group-hover:translate-x-0.5"
            />
          </button>
        </div>
      </div>

      <!-- Hover Border -->
      <div
        class="absolute inset-0 rounded-3xl border-2 border-transparent group-hover:border-blue-200 transition-all duration-500 pointer-events-none"
      ></div>
    </div>
  </NuxtLink>
</template>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
