<template>
  <section class="py-20 bg-white">
    <div class="container mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        <!-- Left Side - Image -->
        <div class="relative">
          <img
            src="https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1000&q=80"
            alt="Team Collaboration"
            class="rounded-3xl shadow-lg w-full h-[550px] object-cover"
          />
          <!-- Floating Element -->
          <div class="absolute -bottom-4 -right-4 bg-secondary text-white p-6 rounded-2xl shadow-xl">
            <div class="text-2xl font-bold">98%</div>
            <div class="text-sm">Success Rate</div>
          </div>
        </div>

        <!-- Right Side - FAQ -->
        <div>
          <div class="mb-12">
            <h2 class="text-5xl font-bold text-gray-900 mb-6">
              Common
              <span class="text-secondary">Questions</span>
            </h2>
            <p class="text-lg text-gray-600">
              Everything you need to know about our platform and courses.
            </p>
          </div>

          <!-- Simple FAQ List -->
          <div class="space-y-6">
            <div
              v-for="(faq, index) in faqs"
              :key="index"
              class="border-b border-gray-200 pb-6"
            >
              <button
                @click="toggleFAQ(index)"
                class="w-full flex items-start justify-between gap-4 text-left group"
              >
                <div class="flex-1">
                  <h3 class="text-xl font-semibold text-gray-900 group-hover:text-secondary transition-colors duration-200">
                    {{ faq.question }}
                  </h3>
                  <div
                    v-show="faq.isOpen"
                    class="mt-3"
                  >
                    <p class="text-gray-600 leading-relaxed">{{ faq.answer }}</p>
                  </div>
                </div>
                <Icon
                  :name="faq.isOpen ? 'heroicons:minus' : 'heroicons:plus'"
                  class="text-secondary text-xl mt-1 flex-shrink-0 transition-transform duration-300"
                  :class="{ 'rotate-180': faq.isOpen }"
                />
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const faqs = ref([
  {
    question: "How long do I have access to the courses?",
    answer: "You get lifetime access to all course materials, including future updates and additional content.",
    isOpen: false
  },
  {
    question: "Are there any prerequisites for the courses?",
    answer: "Most beginner courses require no prior experience. Advanced courses may have specific prerequisites listed in the course description.",
    isOpen: false
  },
  {
    question: "Can I download the course videos?",
    answer: "Yes, you can download videos for offline viewing through our mobile apps. Some courses also provide downloadable resources and code files.",
    isOpen: false
  },
  {
    question: "Do you offer team or enterprise plans?",
    answer: "Yes, we offer special pricing and features for teams and organizations. Contact our sales team for custom enterprise solutions.",
    isOpen: false
  },
  {
    question: "What's your refund policy?",
    answer: "We offer a 30-day money-back guarantee for all courses. If you're not satisfied, you can request a full refund within 30 days of purchase.",
    isOpen: false
  }
]);

const toggleFAQ = (index) => {
  faqs.value[index].isOpen = !faqs.value[index].isOpen;
};
</script>