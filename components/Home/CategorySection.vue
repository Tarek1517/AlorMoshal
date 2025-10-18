<script setup>
const categories = [
  { name: "Web Development", icon: "mdi:code-braces", color: "from-blue-500 to-cyan-500", count: "120" },
  { name: "Data Science", icon: "mdi:chart-bar", color: "from-green-500 to-emerald-500", count: "85" },
  { name: "Mobile Apps", icon: "mdi:cellphone", color: "from-purple-500 to-violet-500", count: "67" },
  { name: "UI/UX Design", icon: "mdi:palette", color: "from-pink-500 to-rose-500", count: "92" },
  { name: "Digital Marketing", icon: "mdi:bullhorn", color: "from-orange-500 to-amber-500", count: "78" },
  { name: "Business", icon: "mdi:briefcase", color: "from-indigo-500 to-blue-500", count: "105" },
  { name: "Photography", icon: "mdi:camera", color: "from-red-500 to-orange-500", count: "54" },
  { name: "Music", icon: "mdi:music", color: "from-yellow-500 to-orange-500", count: "41" },
];
</script>

<template>
  <div class="w-full py-20 bg-gradient-to-br from-slate-50 via-white to-slate-100 relative overflow-hidden">
    <!-- Background Elements -->
    <div class="absolute inset-0 overflow-hidden z-0">
      <div class="absolute top-10 left-10 w-72 h-72 bg-blue-500/5 rounded-full blur-3xl"></div>
      <div class="absolute bottom-10 right-10 w-96 h-96 bg-purple-500/5 rounded-full blur-3xl"></div>
      <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-full h-32 bg-gradient-to-b from-white/40 to-transparent"></div>
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <!-- Section Header -->
      <div class="text-center mb-16">
        <div class="inline-flex items-center gap-3 mb-6">
          <div class="w-2 h-2 bg-gradient-to-r from-primary to-secondary rounded-full"></div>
          <span class="text-sm font-semibold text-gray-600 tracking-wider">LEARNING PATHS</span>
          <div class="w-2 h-2 bg-gradient-to-r from-primary to-secondary rounded-full"></div>
        </div>

        <h2 class="text-5xl md:text-6xl font-bold text-gray-900 mb-6">
          Explore <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Categories</span>
        </h2>
        <p class="text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed">
          Choose your learning journey from our carefully curated course categories designed for skill mastery
        </p>
      </div>

      <!-- Categories Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <div
          v-for="(category, index) in categories"
          :key="category.name"
          class="group relative bg-white rounded-3xl p-8 transition-all duration-500 hover:shadow-2xl border border-gray-200/60 hover:border-transparent hover:-translate-y-2"
        >
          <!-- Background Gradient on Hover -->
          <div class="absolute inset-0 bg-gradient-to-br from-gray-50 to-white rounded-3xl transition-opacity duration-500 group-hover:opacity-0"></div>
          <div 
            :class="`absolute inset-0 bg-gradient-to-br ${category.color} rounded-3xl opacity-0 group-hover:opacity-5 transition-opacity duration-500`"
          ></div>

          <!-- Icon Container -->
          <div class="relative z-10 mb-6">
            <div 
              :class="`w-16 h-16 rounded-2xl bg-gradient-to-br ${category.color} flex items-center justify-center shadow-lg group-hover:shadow-xl transition-all duration-500 group-hover:scale-110`"
            >
              <Icon 
                :name="category.icon" 
                class="text-3xl text-white drop-shadow-sm" 
              />
            </div>
          </div>

          <!-- Content -->
          <div class="relative z-10">
            <h3 class="text-2xl font-bold text-gray-900 mb-3 group-hover:text-gray-800 transition-colors duration-300">
              {{ category.name }}
            </h3>
            <div class="flex items-center justify-between">
              <span class="text-sm text-gray-500 font-medium">
                {{ category.count }} Courses
              </span>
              <div class="flex items-center gap-1 text-primary group-hover:gap-2 transition-all duration-300">
                <span class="text-sm font-semibold">Explore</span>
                <Icon name="heroicons:arrow-right" class="w-4 h-4" />
              </div>
            </div>
          </div>

          <!-- Hover Border Animation -->
          <div 
            :class="`absolute inset-0 rounded-3xl bg-gradient-to-r ${category.color} opacity-0 group-hover:opacity-100 transition-opacity duration-500 -z-10`"
            style="padding: 2px;"
          >
            <div class="w-full h-full bg-white rounded-3xl"></div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>
/* Custom animations for cards */
.grid > div {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInUp 0.6s ease-out forwards;
}

.grid > div:nth-child(1) { animation-delay: 0.1s; }
.grid > div:nth-child(2) { animation-delay: 0.2s; }
.grid > div:nth-child(3) { animation-delay: 0.3s; }
.grid > div:nth-child(4) { animation-delay: 0.4s; }
.grid > div:nth-child(5) { animation-delay: 0.5s; }
.grid > div:nth-child(6) { animation-delay: 0.6s; }
.grid > div:nth-child(7) { animation-delay: 0.7s; }
.grid > div:nth-child(8) { animation-delay: 0.8s; }

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Enhanced hover effects */
.group:hover .group-hover\:scale-110 {
  transform: scale(1.1);
}

.group:hover .group-hover\:gap-2 {
  gap: 0.5rem;
}
</style>