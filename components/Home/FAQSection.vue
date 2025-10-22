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
            <div class="text-2xl font-bold">৯৮%</div>
            <div class="text-sm">সাফল্যের হার</div>
          </div>
        </div>

        <!-- Right Side - FAQ -->
        <div>
          <div class="mb-12">
            <h2 class="text-5xl font-bold text-gray-900 mb-6">
              সাধারণ
              <span class="text-secondary">প্রশ্নসমূহ</span>
            </h2>
            <p class="text-lg text-gray-600">
              আমাদের প্ল্যাটফর্ম এবং কোর্স সম্পর্কিত সমস্ত তথ্য এখানে পাবেন।
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
    question: "আমি কতদিন পর্যন্ত কোর্সগুলোতে প্রবেশাধিকার পাবো?",
    answer: "আপনি সব কোর্সের সামগ্রী আজীবন ব্যবহার করতে পারবেন, এতে ভবিষ্যতের আপডেট এবং অতিরিক্ত কনটেন্টও অন্তর্ভুক্ত।",
    isOpen: false
  },
  {
    question: "কোর্সের জন্য কোনো পূর্বশর্ত আছে কি?",
    answer: "বেশিরভাগ প্রাথমিক কোর্সের জন্য কোনো পূর্ব অভিজ্ঞতার প্রয়োজন নেই। উন্নত কোর্সের ক্ষেত্রে নির্দিষ্ট পূর্বশর্ত কোর্সের বর্ণনায় উল্লেখ থাকে।",
    isOpen: false
  },
  {
    question: "আমি কোর্সের ভিডিও ডাউনলোড করতে পারবো কি?",
    answer: "হ্যাঁ, আপনি আমাদের মোবাইল অ্যাপ ব্যবহার করে অফলাইন ভিডিও দেখতে ডাউনলোড করতে পারবেন। কিছু কোর্সে অতিরিক্ত রিসোর্স এবং কোড ফাইলও ডাউনলোড করা যায়।",
    isOpen: false
  },
  {
    question: "আপনারা টিম বা এন্টারপ্রাইজ প্ল্যান অফার করেন কি?",
    answer: "হ্যাঁ, আমরা টিম এবং প্রতিষ্ঠানগুলোর জন্য বিশেষ মূল্য এবং ফিচার অফার করি। কাস্টম এন্টারপ্রাইজ সমাধানের জন্য আমাদের সেলস টিমের সাথে যোগাযোগ করুন।",
    isOpen: false
  },
  {
    question: "আপনার রিফান্ড নীতি কী?",
    answer: "আমরা সব কোর্সের জন্য ৩০ দিনের মানি-ব্যাক গ্যারান্টি প্রদান করি। যদি আপনি সন্তুষ্ট না হন, তাহলে ক্রয়ের ৩০ দিনের মধ্যে পুরো অর্থ ফেরতের অনুরোধ করতে পারেন।",
    isOpen: false
  }
]);

const toggleFAQ = (index) => {
  faqs.value[index].isOpen = !faqs.value[index].isOpen;
};
</script>
