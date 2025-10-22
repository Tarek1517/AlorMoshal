<template>
  <section
    ref="sectionRef"
    class="w-full relative overflow-hidden py-20 bg-gradient-to-br from-slate-50 via-white to-slate-100"
  >
    <!-- Enhanced Background Elements -->
    <div class="absolute inset-0 overflow-hidden z-0">
      <div
        class="absolute -top-20 -right-20 w-80 h-80 bg-secondary/20 rounded-full blur-3xl animate-pulse-slow"
      ></div>
      <div
        class="absolute -bottom-20 -left-20 w-80 h-80 bg-primary/20 rounded-full blur-3xl animate-pulse-medium"
      ></div>
      <!-- Subtle Grid Pattern -->
      <div class="absolute inset-0 opacity-[0.02]">
        <div
          class="w-full h-full"
          style="
            background-image: radial-gradient(
              circle at 1px 1px,
              #64748b 1px,
              transparent 0
            );
            background-size: 40px 40px;
          "
        ></div>
      </div>
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <!-- Services -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <!-- Card 1: Online Courses -->
        <div
          class="group text-start bg-white/90 backdrop-blur-md rounded-3xl flex p-6 gap-5 transition-all duration-700 hover:shadow-2xl border border-gray-200/60 hover:border-secondary/40 hover:-translate-y-2 relative overflow-hidden"
        >
          <div
            class="absolute inset-0 bg-gradient-to-br from-white to-slate-50/90 z-0"
          ></div>
          <div
            class="absolute -right-8 -top-8 w-24 h-24 bg-secondary/8 rounded-full transition-all duration-700 group-hover:scale-150 group-hover:bg-secondary/12"
          ></div>
          <div
            class="absolute inset-0 bg-gradient-to-r from-transparent via-white/30 to-transparent -skew-x-12 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 z-0"
          ></div>

          <div class="flex justify-start relative z-10">
            <div
              class="p-3 bg-gradient-to-br from-secondary/25 to-secondary/15 rounded-2xl transition-all duration-500 group-hover:scale-110 group-hover:from-secondary/30 group-hover:to-secondary/20 shadow-lg border border-secondary/20 group-hover:shadow-secondary/20"
            >
              <Icon
                name="mdi:book-education"
                class="text-5xl text-secondary drop-shadow-sm"
              />
            </div>
          </div>
          <div class="flex-1 relative z-10">
            <h3
              class="font-black text-4xl text-gray-900 mb-2 tracking-tight bg-gradient-to-br from-gray-900 to-gray-700 bg-clip-text text-transparent"
            >
              <span class="counter" data-target="100">{{
                animatedCounters[0]
              }}</span
              >+
            </h3>
            <p
              class="text-gray-600 text-base font-semibold leading-tight tracking-wide"
            >
              অনলাইন কোর্স
            </p>
          </div>
        </div>

        <!-- Card 2: Expert Instructors -->
        <div
          class="group text-start bg-white/90 backdrop-blur-md rounded-3xl flex gap-5 p-6 transition-all duration-700 hover:shadow-2xl border border-gray-200/60 hover:border-blue-500/40 hover:-translate-y-2 relative overflow-hidden"
        >
          <div
            class="absolute inset-0 bg-gradient-to-br from-white to-slate-50/90 z-0"
          ></div>
          <div
            class="absolute -right-8 -top-8 w-24 h-24 bg-blue-500/8 rounded-full transition-all duration-700 group-hover:scale-150 group-hover:bg-blue-500/12"
          ></div>
          <div
            class="absolute inset-0 bg-gradient-to-r from-transparent via-white/30 to-transparent -skew-x-12 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 z-0"
          ></div>

          <div class="flex justify-start relative z-10">
            <div
              class="p-3 bg-gradient-to-br from-blue-500/25 to-blue-500/15 rounded-2xl transition-all duration-500 group-hover:scale-110 group-hover:from-blue-500/30 group-hover:to-blue-500/20 shadow-lg border border-blue-500/20 group-hover:shadow-blue-500/20"
            >
              <Icon
                name="mdi:account-tie"
                class="text-5xl text-blue-500 drop-shadow-sm"
              />
            </div>
          </div>
          <div class="flex-1 relative z-10">
            <h3
              class="font-black text-4xl text-gray-900 mb-2 tracking-tight bg-gradient-to-br from-gray-900 to-gray-700 bg-clip-text text-transparent"
            >
              <span class="counter" data-target="50">{{
                animatedCounters[1]
              }}</span
              >+
            </h3>
            <p
              class="text-gray-600 text-base font-semibold leading-tight tracking-wide"
            >
              বিশেষজ্ঞ প্রশিক্ষক
            </p>
          </div>
        </div>

        <!-- Card 3: Student Enrollments -->
        <div
          class="group text-start bg-white/90 backdrop-blur-md rounded-3xl flex gap-5 p-6 transition-all duration-700 hover:shadow-2xl border border-gray-200/60 hover:border-green-500/40 hover:-translate-y-2 relative overflow-hidden"
        >
          <div
            class="absolute inset-0 bg-gradient-to-br from-white to-slate-50/90 z-0"
          ></div>
          <div
            class="absolute -right-8 -top-8 w-24 h-24 bg-green-500/8 rounded-full transition-all duration-700 group-hover:scale-150 group-hover:bg-green-500/12"
          ></div>
          <div
            class="absolute inset-0 bg-gradient-to-r from-transparent via-white/30 to-transparent -skew-x-12 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 z-0"
          ></div>

          <div class="flex justify-start relative z-10">
            <div
              class="p-3 bg-gradient-to-br from-green-500/25 to-green-500/15 rounded-2xl transition-all duration-500 group-hover:scale-110 group-hover:from-green-500/30 group-hover:to-green-500/20 shadow-lg border border-green-500/20 group-hover:shadow-green-500/20"
            >
              <Icon
                name="mdi:school"
                class="text-5xl text-green-500 drop-shadow-sm"
              />
            </div>
          </div>
          <div class="flex-1 relative z-10">
            <h3
              class="font-black text-4xl text-gray-900 mb-2 tracking-tight bg-gradient-to-br from-gray-900 to-gray-700 bg-clip-text text-transparent"
            >
              <span class="counter" data-target="10000">{{
                animatedCounters[2]
              }}</span
              >+
            </h3>
            <p
              class="text-gray-600 text-base font-semibold leading-tight tracking-wide"
            >
              শিক্ষার্থী
            </p>
          </div>
        </div>

        <!-- Card 4: Countries Reached -->
        <div
          class="group text-start bg-white/90 backdrop-blur-md rounded-3xl flex p-6 gap-5 transition-all duration-700 hover:shadow-2xl border border-gray-200/60 hover:border-purple-500/40 hover:-translate-y-2 relative overflow-hidden"
        >
          <div
            class="absolute inset-0 bg-gradient-to-br from-white to-slate-50/90 z-0"
          ></div>
          <div
            class="absolute -right-8 -top-8 w-24 h-24 bg-purple-500/8 rounded-full transition-all duration-700 group-hover:scale-150 group-hover:bg-purple-500/12"
          ></div>
          <div
            class="absolute inset-0 bg-gradient-to-r from-transparent via-white/30 to-transparent -skew-x-12 -translate-x-full group-hover:translate-x-full transition-transform duration-1000 z-0"
          ></div>

          <div class="flex justify-start relative z-10">
            <div
              class="p-3 bg-gradient-to-br from-purple-500/25 to-purple-500/15 rounded-2xl transition-all duration-500 group-hover:scale-110 group-hover:from-purple-500/30 group-hover:to-purple-500/20 shadow-lg border border-purple-500/20 group-hover:shadow-purple-500/20"
            >
              <Icon
                name="mdi:earth"
                class="text-5xl text-purple-500 drop-shadow-sm"
              />
            </div>
          </div>
          <div class="flex-1 relative z-10">
            <h3
              class="font-black text-4xl text-gray-900 mb-2 tracking-tight bg-gradient-to-br from-gray-900 to-gray-700 bg-clip-text text-transparent"
            >
              <span class="counter" data-target="35">{{
                animatedCounters[3]
              }}</span
              >+
            </h3>
            <p
              class="text-gray-600 text-base font-semibold leading-tight tracking-wide"
            >
              দেশভিত্তিক পৌঁছনো
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

// Reactive counter values
const animatedCounters = ref([0, 0, 0, 0]);
const sectionRef = ref(null);
const animationStarted = ref(false);

// Target values for each counter
const targetValues = [100, 50, 10000, 35];

// Animation function
const animateCounters = () => {
  if (animationStarted.value) return;

  animationStarted.value = true;
  const duration = 2000; // Animation duration in ms
  const steps = 60; // Number of animation steps
  const stepDuration = duration / steps;

  targetValues.forEach((target, index) => {
    let currentStep = 0;
    const increment = target / steps;

    const timer = setInterval(() => {
      currentStep++;
      animatedCounters.value[index] = Math.min(
        Math.floor(increment * currentStep),
        target
      );

      if (currentStep >= steps) {
        clearInterval(timer);
      }
    }, stepDuration);
  });
};

// Intersection Observer setup
let observer = null;

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting && !animationStarted.value) {
          animateCounters();
        }
      });
    },
    { threshold: 0.3 }
  );

  if (sectionRef.value) {
    observer.observe(sectionRef.value);
  }
});

onUnmounted(() => {
  if (observer && sectionRef.value) {
    observer.unobserve(sectionRef.value);
  }
});
</script>

<style scoped>
/* Custom animations */
@keyframes pulse-slow {
  0%,
  100% {
    opacity: 0.2;
  }
  50% {
    opacity: 0.3;
  }
}

@keyframes pulse-medium {
  0%,
  100% {
    opacity: 0.15;
  }
  50% {
    opacity: 0.25;
  }
}

.animate-pulse-slow {
  animation: pulse-slow 4s ease-in-out infinite;
}

.animate-pulse-medium {
  animation: pulse-medium 3s ease-in-out infinite;
}

/* Enhanced card animations */
.grid > div {
  opacity: 0;
  transform: translateY(20px) scale(0.98);
  animation: cardEntrance 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94) forwards;
}

.grid > div:nth-child(1) {
  animation-delay: 0.1s;
}
.grid > div:nth-child(2) {
  animation-delay: 0.2s;
}
.grid > div:nth-child(3) {
  animation-delay: 0.3s;
}
.grid > div:nth-child(4) {
  animation-delay: 0.4s;
}

@keyframes cardEntrance {
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

/* Enhanced hover effects */
.group:hover {
  transform: translateY(-8px);
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.15),
    0 0 0 1px rgba(255, 255, 255, 0.9) !important;
}

/* Improved icon hover effects */
.group:hover div:first-child > div {
  transform: rotate(3deg) scale(1.1);
  box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.15), 0 0 20px -5px currentColor !important;
}

/* Better number styling */
.counter {
  background: linear-gradient(135deg, #1a202c 0%, #2d3748 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.group:hover .counter {
  background: linear-gradient(135deg, #000000 0%, #1a202c 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
</style>
