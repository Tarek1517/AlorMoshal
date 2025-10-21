<script setup>
import { ref } from "vue";

// Courses data with real image URLs
const courses = [
  {
    id: 1,
    title: "Vue.js Fundamentals",
    category: "Web Development",
    instructor: "John Doe",
    instructorImage: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    image: "https://images.unsplash.com/photo-1633356122544-f134324a6cee?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$49",
    duration: "6 hours",
    level: "Beginner",
    rating: 4.8,
    students: 1245,
    featured: true,
    instructorBio: "Senior Frontend Developer with 8+ years of experience. Specialized in Vue.js and modern JavaScript frameworks.",
    instructorCourses: 12,
    instructorStudents: 15420
  },
  
  {
    id: 3,
    title: "Python for Data Science",
    category: "Data Science",
    instructor: "Alice Johnson",
    instructorImage: "https://images.unsplash.com/photo-1580489944761-15a19d654956?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    image: "https://images.unsplash.com/photo-1526379879527-8559ecfcaec0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$69",
    duration: "10 hours",
    level: "Intermediate",
    rating: 4.7,
    students: 2103,
    featured: false,
    instructorBio: "Data Scientist at TechCorp with PhD in Machine Learning. Published researcher in AI journals.",
    instructorCourses: 6,
    instructorStudents: 12500
  },
  {
    id: 4,
    title: "UI/UX Design Essentials",
    category: "Design",
    instructor: "Mark Lee",
    instructorImage: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    image: "https://images.unsplash.com/photo-1561070791-2526d30994b5?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$39",
    duration: "5 hours",
    level: "Beginner",
    rating: 4.6,
    students: 1567,
    featured: false,
    instructorBio: "Lead Product Designer at DesignStudio. 10+ years of experience in creating user-centered designs.",
    instructorCourses: 10,
    instructorStudents: 18700
  },
  {
    id: 5,
    title: "Machine Learning Mastery",
    category: "AI & ML",
    instructor: "Emma Davis",
    instructorImage: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    image: "https://images.unsplash.com/photo-1555949963-ff9fe0c870eb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    price: "$79",
    duration: "12 hours",
    level: "Advanced",
    rating: 4.9,
    students: 987,
    featured: true,
    instructorBio: "AI Research Lead at AI Labs. Former Stanford professor with publications in top ML conferences.",
    instructorCourses: 7,
    instructorStudents: 11200
  },
  
];

// Extract unique instructors
const instructors = [...new Map(courses.map(course => [course.instructor, {
  name: course.instructor,
  image: course.instructorImage,
  coursesCount: course.instructorCourses,
  studentsCount: course.instructorStudents,
  rating: course.rating,
  category: course.category
}])).values()];

const visibleInstructors = ref(4);
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
          <Icon
            name="carbon:ibm-software-watsonx-data-structured-enrichment"
            class="text-secondary text-2xl"
          />
          Expert-Led Learning Experience
        </div>
        <h2
          class="text-5xl md:text-6xl font-bold text-gray-900 mb-6 leading-tight"
        >
          Learn from
          <span
            class="text-transparent bg-clip-text bg-gradient-to-r from-secondary to-primary"
            >Industry Experts</span
          >
        </h2>
        <p class="text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed">
          Our instructors are seasoned professionals with real-world experience, ready to share their knowledge and help you succeed.
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
          <span>View All Instructors</span>
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
