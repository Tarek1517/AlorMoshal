<script setup>
const blogs = [
  {
    id: 1,
    title: "How to Import Your Dream Car Easily",
    category: "Guides",
    excerpt: "Learn step-by-step how to import cars from Japan with minimal hassle and maximum savings. Our comprehensive guide covers everything from documentation to delivery.",
    image:  "https://images.unsplash.com/photo-1605379399642-870262d3d051?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    author: "John Doe",
    authorImage: "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/how-to-import-car",
    publishDate: "2024-01-15",
    readTime: "8 min read",
    tags: ["Import", "Guide", "Cars"]
  },
  {
    id: 2,
    title: "Top 5 Reliable Car Brands in 2024",
    category: "Reviews",
    excerpt: "We break down the most reliable brands this year, helping you choose wisely based on performance, maintenance costs, and customer satisfaction.",
    image: "https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    author: "Sarah Ali",
     authorImage: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/reliable-car-brands",
    publishDate: "2024-01-10",
    readTime: "6 min read",
    tags: ["Reviews", "Brands", "2024"]
  },
  
  {
    id: 4,
    title: "Electric Vehicles: The Complete Buyer's Guide",
    category: "EV",
    excerpt: "Everything you need to know before buying an electric vehicle. From charging infrastructure to maintenance costs and government incentives.",
    image: "https://images.unsplash.com/photo-1605379399642-870262d3d051?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    author: "Emma Davis",
    authorImage: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/ev-buyers-guide",
    publishDate: "2024-01-02",
    readTime: "12 min read",
    tags: ["EV", "Guide", "Electric"]
  },
  
  {
    id: 6,
    title: "The Rise of Autonomous Driving Technology",
    category: "Technology",
    excerpt: "Exploring the latest advancements in autonomous driving and what it means for the future of transportation and car ownership.",
    image: "https://images.unsplash.com/photo-1633356122544-f134324a6cee?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80",
    author: "Alex Chen",
    authorImage: "https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/autonomous-driving",
    publishDate: "2023-12-25",
    readTime: "9 min read",
    tags: ["Technology", "Autonomous", "Future"]
  }
];
</script>

<template>
  <div class="w-full py-20 bg-gradient-to-br from-gray-50 to-white relative overflow-hidden">
    <!-- Background Elements -->
    <div class="absolute top-10 right-10 w-72 h-72 bg-blue-100/30 rounded-full blur-3xl"></div>
    <div class="absolute bottom-10 left-10 w-96 h-96 bg-purple-100/20 rounded-full blur-3xl"></div>

    <!-- Section Header -->
    <div class="text-center mb-14 relative z-10">
      <div
        class="inline-flex items-center px-4 py-2 bg-white/80 backdrop-blur-sm border border-primary/20 text-secondary rounded-full text-sm font-semibold mb-4 shadow-sm"
      >
        <Icon name="heroicons:newspaper" class="w-4 h-4 mr-2" />
        Latest Articles
      </div>

      <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
        Our Recent
        <span
          class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
          >News & Articles</span
        >
      </h2>
      <p
        class="text-lg md:text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed"
      >
        Discover expert insights, guides, and reviews to help you make informed decisions about your next vehicle.
      </p>
    </div>

    <!-- Blog Carousel -->
    <div class="container mx-auto px-6 mt-12 relative z-10">
      <UCarousel
        :items="blogs"
        loop
        auto-scroll
        :slides-per-view="3"
        :slide-to-scroll="1"
        class="overflow-visible"
        :ui="{ item: 'basis-full sm:basis-1/2 lg:basis-1/3 p-4' }"
      >
        <template #default="{ item }">
          <!-- Equal height wrapper -->
          <div class="h-[480px]">
            <BlogCard :blog="item" class="w-full h-full flex flex-col" />
          </div>
        </template>
      </UCarousel>
    </div>

    <!-- View All Articles Button -->
    <div class="text-center mt-12 relative z-10">
      <button class="px-8 py-4 bg-gradient-to-r from-primary to-secondary text-white rounded-full font-semibold hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center justify-center gap-2 mx-auto">
        <span>View All Articles</span>
        <Icon name="heroicons:arrow-right" class="text-lg" />
      </button>
    </div>
  </div>
</template>

<style scoped>

</style>