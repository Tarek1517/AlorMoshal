<script setup>
import { ref } from "vue";

// Courses data with real image URLs
const courses = [
  {
    id: 1,
    title: "ভিউ.জেএস ফান্ডামেন্টালস",
    category: "ওয়েব ডেভেলপমেন্ট",
    instructor: "জন ডো",
    instructorImage:
      "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    image:
      "https://images.unsplash.com/photo-1633356122544-f134324a6cee?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳4900",
    duration: "৬ ঘণ্টা",
    level: "শুরুতি",
    rating: 4.8,
    students: 1245,
    featured: true,
    instructorBio:
      "সিনিয়র ফ্রন্টএন্ড ডেভেলপার ৮+ বছরের অভিজ্ঞতাসহ। ভিউ.জেএস ও আধুনিক জাভাস্ক্রিপ্ট ফ্রেমওয়ার্কে বিশেষজ্ঞ।",
    instructorCourses: 12,
    instructorStudents: 15420,
  },

  {
    id: 3,
    title: "ডেটা সায়েন্সের জন্য পাইথন",
    category: "ডেটা সায়েন্স",
    instructor: "অ্যালিস জনসন",
    instructorImage:
      "https://images.unsplash.com/photo-1580489944761-15a19d654956?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    image:
      "https://images.unsplash.com/photo-1526379879527-8559ecfcaec0?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳6900",
    duration: "১০ ঘণ্টা",
    level: "মধ্যবর্তী",
    rating: 4.7,
    students: 2103,
    featured: false,
    instructorBio:
      "টেককপোর এআই ডেটা সায়েন্টিস্ট। মেশিন লার্নিং-এ পিএইচডি এবং প্রকাশিত গবেষক।",
    instructorCourses: 6,
    instructorStudents: 12500,
  },
  {
    id: 4,
    title: "UI/UX ডিজাইন এসেনশিয়ালস",
    category: "UI/UX ডিজাইন",
    instructor: "মার্ক লি",
    instructorImage:
      "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    image:
      "https://images.unsplash.com/photo-1561070791-2526d30994b5?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳3900",
    duration: "৫ ঘণ্টা",
    level: "শুরুতি",
    rating: 4.6,
    students: 1567,
    featured: false,
    instructorBio:
      "লিড প্রোডাক্ট ডিজাইনার। ১০+ বছরের ব্যবহারকারী-কেন্দ্রিক ডিজাইন অভিজ্ঞতা।",
    instructorCourses: 10,
    instructorStudents: 18700,
  },
  {
    id: 5,
    title: "মেশিন লার্নিং মাস্টারি",
    category: "ডেটা সায়েন্স",
    instructor: "এমা ডেভিস",
    instructorImage:
      "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    image:
      "https://images.unsplash.com/photo-1555949963-ff9fe0c870eb?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳7900",
    duration: "১২ ঘণ্টা",
    level: "উন্নত",
    rating: 4.9,
    students: 987,
    featured: true,
    instructorBio:
      "এআই রিসার্চ লিড। স্ট্যানফোর্ড প্রফেসর। শীর্ষ ML কনফারেন্সে প্রকাশিত।",
    instructorCourses: 7,
    instructorStudents: 11200,
  },
];

// Extract unique instructors
const instructors = [
  ...new Map(
    courses.map((course) => [
      course.instructor,
      {
        name: course.instructor,
        image: course.instructorImage,
        coursesCount: course.instructorCourses,
        studentsCount: course.instructorStudents,
        rating: course.rating,
        category: course.category,
      },
    ])
  ).values(),
];

const visibleInstructors = ref(4);
const activeCategory = ref("All");
</script>

<template>
  <div
    class="py-20 bg-gradient-to-br from-slate-50 to-blue-50 relative overflow-hidden"
  >
    <!-- Background shapes -->
    <div
      class="absolute top-10 left-10 w-80 h-80 bg-blue-100/30 rounded-full blur-3xl"
    ></div>
    <div
      class="absolute bottom-10 right-10 w-96 h-96 bg-purple-100/30 rounded-full blur-3xl"
    ></div>
    <div
      class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-64 h-64 bg-cyan-100/20 rounded-full blur-3xl"
    ></div>

    <div class="container mx-auto px-6 relative z-10">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div
          class="inline-flex items-center gap-2 px-4 py-2 bg-white/80 backdrop-blur-sm text-secondary rounded-full text-sm font-medium mb-6 shadow-sm"
        >
          <Icon
            name="carbon:ibm-software-watsonx-data-structured-enrichment"
            class="text-secondary text-2xl"
          />
          বিশেষজ্ঞদের নেতৃত্বে শেখার অভিজ্ঞতা
        </div>
        <h2
          class="text-5xl md:text-6xl font-bold text-gray-900 mb-6 leading-tight"
        >
          শিখুন
          <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-secondary to-primary"
            >বিশেষজ্ঞদের </span
          >কাছ থেকে
        </h2>
        <p class="text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed">
          আমাদের প্রশিক্ষকরা বাস্তব অভিজ্ঞতাসম্পন্ন পেশাদার, যারা তাদের জ্ঞান
          শেয়ার করতে প্রস্তুত এবং আপনার সফলতা নিশ্চিত করবে।
        </p>
      </div>

      <!-- Instructors Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-16">
        <InstructorCard
          v-for="instructor in instructors.slice(0, visibleInstructors)"
          :key="instructor.name"
          :instructor="instructor"
          class="w-full transform hover:scale-105 transition-transform duration-300"
        />
      </div>

      <!-- Load More Button -->
      <div class="text-center">
        <button
          class="px-8 py-4 bg-secondary text-white rounded-full font-semibold hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center justify-center gap-2 mx-auto"
        >
          সব প্রশিক্ষক দেখুন
          <Icon name="heroicons:arrow-right" class="text-lg" />
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Custom scrollbar for category filter */
::-webkit-scrollbar {
  height: 6px;
}
::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 10px;
}
::-webkit-scrollbar-thumb {
  background: #c1c1c1;
  border-radius: 10px;
}
::-webkit-scrollbar-thumb:hover {
  background: #a8a8a8;
}
</style>
