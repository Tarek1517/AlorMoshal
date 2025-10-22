<script setup>
import { ref } from "vue";

// Courses data in Bangla with relevant categories
const courses = [
  {
    id: 1,
    title: "বাংলা ব্যাকরণ ও সাহিত্য",
    category: "বাংলা",
    instructor: "মোঃ রহমান",
    image:
      "https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳499",
    duration: "8 ঘন্টা",
    level: "শুরুতি",
    rating: 4.8,
    students: 1245,
    featured: true,
  },
  {
    id: 2,
    title: "ইংরেজি ভাষার দক্ষতা উন্নয়ন",
    category: "ইংরেজি",
    instructor: "জেন স্মিথ",
    image:
      "https://images.unsplash.com/photo-1516321318423-f06f85e504b3?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳599",
    duration: "10 ঘন্টা",
    level: "মধ্যবর্তী",
    rating: 4.9,
    students: 892,
    featured: true,
  },
  {
    id: 3,
    title: "বিসিএস প্রস্তুতি কোর্স",
    category: "বিসিএস",
    instructor: "আলিস জনসন",
    image:
      "https://images.unsplash.com/photo-1541339907198-e08756dedf3f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳699",
    duration: "12 ঘন্টা",
    level: "উন্নত",
    rating: 4.7,
    students: 2103,
    featured: false,
  },
  {
    id: 4,
    title: "শিক্ষক নিয়োগ/নিবন্ধন প্রস্তুতি",
    category: "শিক্ষক নিয়োগ/নিবন্ধন",
    instructor: "মার্ক লি",
    image:
      "https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳549",
    duration: "9 ঘন্টা",
    level: "মধ্যবর্তী",
    rating: 4.6,
    students: 1567,
    featured: false,
  },
  {
    id: 5,
    title: "ভর্তি প্রস্তুতি বিশেষ কোর্স",
    category: "ভর্তি প্রস্তুতি",
    instructor: "এমা ডেভিস",
    image:
      "https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳399",
    duration: "6 ঘন্টা",
    level: "শুরুতি",
    rating: 4.9,
    students: 987,
    featured: true,
  },
  {
    id: 6,
    title: "একাডেমিক স্টাডি ও নোটস",
    category: "একাডেমিক স্টাডি",
    instructor: "টম ব্রাউন",
    image:
      "https://images.unsplash.com/photo-1516321318423-f06f85e504b3?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳349",
    duration: "5 ঘন্টা",
    level: "শুরুতি",
    rating: 4.5,
    students: 3102,
    featured: false,
  },
  {
    id: 7,
    title: "কম্পিউটার ও IT দক্ষতা",
    category: "কম্পিউটার ও IT",
    instructor: "সারা উইলসন",
    image:
      "https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳799",
    duration: "15 ঘন্টা",
    level: "উন্নত",
    rating: 4.8,
    students: 745,
    featured: true,
  },
  {
    id: 8,
    title: "কোচিং ও প্রশিক্ষণ",
    category: "কোচিং ও প্রশিক্ষণ",
    instructor: "অ্যালেক্স চেন",
    image:
      "https://images.unsplash.com/photo-1605379399642-870262d3d051?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    price: "৳899",
    duration: "14 ঘন্টা",
    level: "মধ্যবর্তী",
    rating: 4.9,
    students: 1560,
    featured: true,
  },
];

const visibleCourses = ref(8);
</script>

<template>
  <div
    class="py-20 bg-gradient-to-br from-slate-50 to-blue-50 relative overflow-hidden"
  >
    <!-- Modern background elements -->
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
          <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            />
          </svg>
          সেরা অনলাইন কোর্স
        </div>
        <h2
          class="text-5xl md:text-6xl font-bold text-gray-900 mb-6 leading-tight"
        >
          আপনার জ্ঞান সম্প্রসারণ করুন
          <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-secondary to-primary"
            >শিখুন</span
          >
        </h2>
        <p class="text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed">
          শিল্প বিশেষজ্ঞদের হাতে নির্বাচিত কোর্সগুলো আপনার দক্ষতা বৃদ্ধি এবং ক্যারিয়ার উন্নয়নের জন্য।
        </p>
      </div>

      <!-- Courses Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-16">
        <CourseCard
          v-for="course in courses.slice(0, visibleCourses)"
          :key="course.id"
          :course="course"
          class="w-full transform hover:scale-105 transition-transform duration-300"
        />
      </div>

      <!-- Load More Button -->
      <div class="text-center">
        <button
          class="px-8 py-4 bg-secondary text-white rounded-full font-semibold hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1"
        >
          আরও কোর্স দেখুন
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
