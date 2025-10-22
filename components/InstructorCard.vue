<template>
  <div
    class="bg-white rounded-2xl shadow-lg overflow-hidden border border-gray-100 hover:shadow-xl transition-all duration-300 group relative"
  >
    <!-- Circular Instructor Image -->
    <div class="relative pt-8 pb-4 flex justify-center">
      <div class="relative">
        <img
          :src="instructor.image"
          :alt="instructor.name"
          class="w-48 h-48 rounded-full object-cover border-4 border-white shadow-lg transition-transform duration-500 group-hover:scale-110"
        />
        <!-- Online Status Indicator -->
        <div
          class="absolute bottom-2 right-2 w-4 h-4 bg-green-500 rounded-full border-2 border-white"
        ></div>
      </div>
    </div>

    <!-- Instructor Info -->
    <div class="p-6 pt-2">
      <!-- Name and Category -->
      <div class="text-center">
        <h3 class="text-xl font-bold text-gray-900 mb-2">
          {{ instructor.name }}
        </h3>
        <div
          class="inline-flex items-center gap-1 px-3 py-1 bg-blue-50 text-blue-600 rounded-full text-sm font-medium"
        >
          <Icon
            name="carbon:ibm-software-watsonx-data-structured-enrichment"
            class="text-sm"
          />
          {{ instructor.category }}
        </div>
      </div>

      <!-- Bio -->
      <p
        class="text-gray-600 text-sm leading-relaxed mb-3 text-center line-clamp-2"
      >
        {{ instructor.bio }}
      </p>

      <!-- Stats -->
      <div class="grid grid-cols-2 gap-4 mb-3">
        <div class="text-center">
          <div class="text-2xl font-bold text-secondary">
            {{ instructor.coursesCount }}+
          </div>
          <div class="text-xs text-gray-500 uppercase tracking-wide">
            কোর্স
          </div>
        </div>
        <div class="text-center">
          <div class="text-2xl font-bold text-primary">
            {{ Math.floor(instructor.studentsCount / 1000) }}K+
          </div>
          <div class="text-xs text-gray-500 uppercase tracking-wide">
            শিক্ষার্থী
          </div>
        </div>
      </div>

      <!-- Social Media Share Icons -->
      <div class="flex justify-center gap-3 pt-4 border-t border-gray-100">
        <button
          @click="shareOnFacebook"
          class="w-6 h-6 bg-blue-600 text-white rounded-full flex items-center justify-center hover:bg-blue-700 transition-colors duration-300 hover:scale-110"
        >
          <Icon name="ri:facebook-fill" class="text-base" />
        </button>
        <button
          @click="shareOnTwitter"
          class="w-6 h-6 bg-sky-500 text-white rounded-full flex items-center justify-center hover:bg-sky-600 transition-colors duration-300 hover:scale-110"
        >
          <Icon name="ri:twitter-x-fill" class="text-base" />
        </button>
        <button
          @click="shareOnLinkedIn"
          class="w-6 h-6 bg-blue-800 text-white rounded-full flex items-center justify-center hover:bg-blue-900 transition-colors duration-300 hover:scale-110"
        >
          <Icon name="ri:linkedin-fill" class="text-base" />
        </button>
        <button
          @click="shareOnInstagram"
          class="w-6 h-6 bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-full flex items-center justify-center hover:from-purple-600 hover:to-pink-600 transition-colors duration-300 hover:scale-110"
        >
          <Icon name="ri:instagram-fill" class="text-base" />
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  instructor: {
    type: Object,
    required: true,
  },
});

// সোশ্যাল শেয়ার ফাংশন
const shareOnFacebook = () => {
  const url = encodeURIComponent(window.location.href);
  const text = encodeURIComponent(
    `${props.instructor.name}-এর প্রোফাইল দেখুন!`
  );
  window.open(
    `https://www.facebook.com/sharer/sharer.php?u=${url}&quote=${text}`,
    "_blank"
  );
};

const shareOnTwitter = () => {
  const text = encodeURIComponent(
    `${props.instructor.name}-এর প্রোফাইল দেখুন! অসাধারণ প্রশিক্ষক ${props.instructor.category} এ।`
  );
  const url = encodeURIComponent(window.location.href);
  window.open(
    `https://twitter.com/intent/tweet?text=${text}&url=${url}`,
    "_blank"
  );
};

const shareOnLinkedIn = () => {
  const url = encodeURIComponent(window.location.href);
  window.open(
    `https://www.linkedin.com/sharing/share-offsite/?url=${url}`,
    "_blank"
  );
};

const shareOnInstagram = () => {
  const profileLink = `${
    window.location.href
  }/instructor/${props.instructor.name.toLowerCase().replace(/\s+/g, "-")}`;
  navigator.clipboard.writeText(profileLink).then(() => {
    alert("প্রোফাইল লিংক ক্লিপবোর্ডে কপি হয়েছে! এটি ইনস্টাগ্রামে শেয়ার করতে পারেন।");
  });
};
</script>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
