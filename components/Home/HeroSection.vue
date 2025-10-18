<template>
  <section
    class="relative h-[600px] flex items-center justify-center overflow-hidden"
  >
    <!-- Background Slider -->
    <div class="absolute inset-0">
      <UCarousel
        v-slot="{ item }"
        :items="carouselItems"
        :ui="{
          item: 'flex-[0_0_100%]',
          container: 'w-full h-full',
        }"
        class="w-full h-full"
        arrows
        indicators
        autoplay
      >
        <div class="relative w-full h-full">
          <img
            :src="item.image"
            :alt="item.title"
            class="w-full h-full object-cover"
          />
          <!-- Dark Overlay for better text readability -->
          <div class="absolute inset-0 bg-black/40"></div>
        </div>
      </UCarousel>
    </div>

    <!-- Content Overlay -->
    <div
      class="relative z-10 w-full max-w-6xl mx-auto px-4 text-center text-white"
    >
      <div class="space-y-4">
        <!-- Main Heading -->
        <h1 class="text-4xl lg:text-6xl font-bold leading-tight">
          Unlock Your
          <span
            class="bg-gradient-to-r from-secondary to-primary bg-clip-text text-transparent"
          >
            Potential
          </span>
        </h1>
        <!-- Description -->
        <p
          class="text-lg lg:text-xl text-gray-200 leading-relaxed max-w-2xl mx-auto"
        >
          Transform your career with our comprehensive learning platform.
        </p>

        <!-- CTA Buttons -->
        <div
          class="flex flex-col sm:flex-row gap-4 justify-center items-center"
        >
          <button
            class="bg-primary hover:bg-secondary text-white px-8 py-4 rounded-xl font-semibold text-lg shadow-2xl transition-all duration-300 hover:scale-105 flex items-center justify-center gap-3 min-w-[200px]"
          >
            <Icon name="mdi:rocket-launch" class="text-lg" />
            Get Started Free
          </button>
          <button
            class="bg-secondary hover:bg-primary text-white px-8 py-4 rounded-xl font-semibold text-lg shadow-2xl transition-all duration-300 hover:scale-105 flex items-center justify-center gap-3 min-w-[200px]"
          >
            <Icon name="mdi:play-circle" class="text-lg" />
            Watch Demo
          </button>
        </div>

        <!-- Icon Boxes with Courses -->
        <div
          class="grid grid-cols-2 lg:grid-cols-6 gap-4 pt-3 max-w-4xl mx-auto"
        >
          <div
            class="bg-blue-500/90 backdrop-blur-sm rounded-xl p-4 text-center hover:scale-105 transition-transform duration-300 cursor-pointer"
          >
            <div
              class="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center mx-auto mb-3"
            >
              <Icon
                name="material-symbols-light:globe-uk-sharp"
                class="text-white text-2xl"
              />
            </div>
            <h3 class="font-semibold text-white">Business</h3>
          </div>

          <div
            class="bg-purple-500/90 backdrop-blur-sm rounded-xl p-4 text-center hover:scale-105 transition-transform duration-300 cursor-pointer"
          >
            <div
              class="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center mx-auto mb-3"
            >
              <Icon name="mdi:chart-bar" class="text-white text-2xl" />
            </div>
            <h3 class="font-semibold text-white">Data Science</h3>
          </div>

          <div
            class="bg-green-500/90 backdrop-blur-sm rounded-xl p-4 text-center hover:scale-105 transition-transform duration-300 cursor-pointer"
          >
            <div
              class="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center mx-auto mb-3"
            >
              <Icon name="mdi:palette" class="text-white text-2xl" />
            </div>
            <h3 class="font-semibold text-white">UI/UX Design</h3>
          </div>

          <div
            class="bg-orange-500/90 backdrop-blur-sm rounded-xl p-4 text-center hover:scale-105 transition-transform duration-300 cursor-pointer"
          >
            <div
              class="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center mx-auto mb-3"
            >
              <Icon name="mdi:cellphone" class="text-white text-2xl" />
            </div>
            <h3 class="font-semibold text-white">Mobile Apps</h3>
          </div>
          <div
            class="bg-emerald-500/90 backdrop-blur-sm rounded-xl p-4 text-center hover:scale-105 transition-transform duration-300 cursor-pointer"
          >
            <div
              class="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center mx-auto mb-3"
            >
              <Icon
                name="carbon:ibm-software-watsonx-data-structured-enrichment"
                class="text-white text-2xl"
              />
            </div>
            <h3 class="font-semibold text-white">Software</h3>
          </div>
          <div
            class="bg-fuchsia-500/90 backdrop-blur-sm rounded-xl p-4 text-center hover:scale-105 transition-transform duration-300 cursor-pointer"
          >
            <div
              class="w-12 h-12 bg-white/20 rounded-lg flex items-center justify-center mx-auto mb-3"
            >
              <Icon name="streamline-freehand:help-headphones-customer-support-human" class="text-white text-2xl" />
            </div>
            <h3 class="font-semibold text-white">Coaching</h3>
          </div>
        </div>

        <!-- Trust Badges -->
        <div class="flex flex-wrap justify-center gap-6 pt-6">
          <div
            class="flex items-center gap-3 bg-white/10 backdrop-blur-sm px-4 py-2 rounded-lg"
          >
            <Icon name="mdi:shield-check" class="text-green-400 text-xl" />
            <span class="text-sm font-medium">30-Day Guarantee</span>
          </div>
          <div
            class="flex items-center gap-3 bg-white/10 backdrop-blur-sm px-4 py-2 rounded-lg"
          >
            <Icon name="mdi:certificate" class="text-blue-400 text-xl" />
            <span class="text-sm font-medium">Certificates</span>
          </div>
          <div
            class="flex items-center gap-3 bg-white/10 backdrop-blur-sm px-4 py-2 rounded-lg"
          >
            <Icon name="mdi:clock-outline" class="text-purple-400 text-xl" />
            <span class="text-sm font-medium">Self-Paced</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Carousel items with full-width background images
const carouselItems = [
  {
    id: 1,
    image:
      "https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80",
    title: "Collaborative Learning Environment",
  },
  {
    id: 2,
    image:
      "https://images.unsplash.com/photo-1516321318423-f06f85e504b3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80",
    title: "Modern Digital Classroom",
  },
  {
    id: 3,
    image:
      "https://images.unsplash.com/photo-1535223289827-42f1e9919769?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80",
    title: "Interactive Online Courses",
  },
  {
    id: 4,
    image:
      "https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80",
    title: "Professional Skill Development",
  },
  {
    id: 5,
    image:
      "https://images.unsplash.com/photo-1541339907198-e08756dedf3f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80",
    title: "Global Learning Community",
  },
];
</script>

<style scoped></style>
