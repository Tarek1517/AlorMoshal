<script setup>
import { ref } from "vue";

// Courses data with real image URLs
const courses = [
  {
    id: 1,
    title: "Vue.js Fundamentals",
    category: "Web Development",
    instructor: "John Doe",
    image:
      "https://images.unsplash.com/photo-1633356122544-f134324a6cee?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$49",
    duration: "6 hours",
    level: "Beginner",
    rating: 4.8,
    students: 1245,
    featured: true,
  },
  {
    id: 2,
    title: "Advanced React",
    category: "Web Development",
    instructor: "Jane Smith",
    image:
      "https://images.unsplash.com/photo-1633356122102-3fe601e05bd2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$59",
    duration: "8 hours",
    level: "Advanced",
    rating: 4.9,
    students: 892,
    featured: true,
  },
  {
    id: 3,
    title: "Python for Data Science",
    category: "Data Science",
    instructor: "Alice Johnson",
    image:
      "https://images.unsplash.com/photo-1526379879527-8559ecfcaec0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$69",
    duration: "10 hours",
    level: "Intermediate",
    rating: 4.7,
    students: 2103,
    featured: false,
  },
  {
    id: 4,
    title: "UI/UX Design Essentials",
    category: "Design",
    instructor: "Mark Lee",
    image:
      "https://images.unsplash.com/photo-1561070791-2526d30994b5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$39",
    duration: "5 hours",
    level: "Beginner",
    rating: 4.6,
    students: 1567,
    featured: false,
  },
  {
    id: 5,
    title: "Machine Learning Mastery",
    category: "AI & ML",
    instructor: "Emma Davis",
    image:
      "https://images.unsplash.com/photo-1555949963-ff9fe0c870eb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$79",
    duration: "12 hours",
    level: "Advanced",
    rating: 4.9,
    students: 987,
    featured: true,
  },
  {
    id: 6,
    title: "Digital Marketing 101",
    category: "Marketing",
    instructor: "Tom Brown",
    image:
      "https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$29",
    duration: "4 hours",
    level: "Beginner",
    rating: 4.5,
    students: 3102,
    featured: false,
  },
  {
    id: 7,
    title: "Fullstack Web Development",
    category: "Web Development",
    instructor: "Sara Wilson",
    image:
      "https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$99",
    duration: "15 hours",
    level: "Advanced",
    rating: 4.8,
    students: 745,
    featured: true,
  },
  {
    id: 8,
    title: "Next.js 14 & Modern Fullstack",
    category: "Web Development",
    instructor: "Alex Chen",
    image:
      "https://images.unsplash.com/photo-1605379399642-870262d3d051?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$89",
    duration: "14 hours",
    level: "Intermediate",
    rating: 4.9,
    students: 1560,
    featured: true,
  },
];

const visibleCourses = ref(8);
const activeCategory = ref("All");
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
      <!-- Modern Section Header -->
      <div class="text-center mb-16">
        <div
          class="inline-flex items-center gap-2 px-4 py-2 bg-white/80 backdrop-blur-sm text-secondary rounded-full text-sm font-medium mb-6 shadow-sm"
        >
          <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20">
            <path
              d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
            />
          </svg>
          Premium Learning Experience
        </div>
        <h2
          class="text-5xl md:text-6xl font-bold text-gray-900 mb-6 leading-tight"
        >
          Expand Your
          <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-secondary to-primary"
            >Knowledge</span
          >
        </h2>
        <p class="text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed">
          Hand-picked courses from industry experts to accelerate your career
          growth and skill development.
        </p>
      </div>

      <!-- Courses Grid with CourseCard Components -->
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
          Load More Courses
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
