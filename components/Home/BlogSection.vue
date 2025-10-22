<script setup>
const blogs = [
  {
    id: 1,
    title: "আপনার স্বপ্নের গাড়ি কিভাবে সহজে আমদানি করবেন",
    category: "গাইড",
    excerpt:
      "জাপান থেকে গাড়ি আমদানির ধাপে ধাপে নির্দেশনা, যেখানে ন্যূনতম ঝামেলা এবং সর্বাধিক সঞ্চয় নিশ্চিত। আমাদের পূর্ণাঙ্গ গাইড ডকুমেন্টেশন থেকে ডেলিভারি পর্যন্ত সবকিছু কভার করে।",
    image:
      "https://images.unsplash.com/photo-1605379399642-870262d3d051?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    author: "জন ডো",
    authorImage:
      "https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/how-to-import-car",
    publishDate: "2024-01-15",
    readTime: "৮ মিনিটে পড়া যায়",
    tags: ["আমদানি", "গাইড", "গাড়ি"],
  },
  {
    id: 2,
    title: "২০২৪ সালে শীর্ষ ৫ নির্ভরযোগ্য গাড়ি ব্র্যান্ড",
    category: "রিভিউ",
    excerpt:
      "এই বছরের সবচেয়ে নির্ভরযোগ্য ব্র্যান্ডগুলি আমরা বিশ্লেষণ করেছি, যা আপনাকে পারফরম্যান্স, রক্ষণাবেক্ষণ খরচ এবং কাস্টমার সন্তুষ্টির ভিত্তিতে বুদ্ধিমানের মতো নির্বাচন করতে সাহায্য করবে।",
    image:
      "https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    author: "সারাহ আলী",
    authorImage:
      "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/reliable-car-brands",
    publishDate: "2024-01-10",
    readTime: "৬ মিনিটে পড়া যায়",
    tags: ["রিভিউ", "ব্র্যান্ড", "২০২৪"],
  },
  {
    id: 4,
    title: "ইলেকট্রিক ভেহিকল: পূর্ণাঙ্গ ক্রেতা গাইড",
    category: "ইভি",
    excerpt:
      "ইলেকট্রিক গাড়ি কেনার আগে যা যা জানা প্রয়োজন। চার্জিং অবকাঠামো থেকে রক্ষণাবেক্ষণ খরচ এবং সরকারি প্রণোদনা পর্যন্ত সবকিছু।",
    image:
      "https://images.unsplash.com/photo-1605379399642-870262d3d051?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    author: "এমা ডেভিস",
    authorImage:
      "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/ev-buyers-guide",
    publishDate: "2024-01-02",
    readTime: "১২ মিনিটে পড়া যায়",
    tags: ["ইভি", "গাইড", "ইলেকট্রিক"],
  },
  {
    id: 6,
    title: "স্বয়ংক্রিয় চালনার প্রযুক্তির উত্থান",
    category: "প্রযুক্তি",
    excerpt:
      "স্বয়ংক্রিয় চালনার সর্বশেষ উন্নয়ন এবং এটি ভবিষ্যতের পরিবহন ও গাড়ি মালিকানার জন্য কী অর্থ রাখে তা বিশ্লেষণ।",
    image:
      "https://images.unsplash.com/photo-1633356122544-f134324a6cee?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80",
    author: "অ্যালেক্স চেন",
    authorImage:
      "https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
    link: "/blogs/autonomous-driving",
    publishDate: "2023-12-25",
    readTime: "৯ মিনিটে পড়া যায়",
    tags: ["প্রযুক্তি", "স্বয়ংক্রিয়", "ভবিষ্যৎ"],
  },
];
</script>

<template>
  <div
    class="w-full py-20 bg-gradient-to-br from-gray-50 to-white relative overflow-hidden"
  >
    <!-- Background Elements -->
    <div
      class="absolute top-10 right-10 w-72 h-72 bg-blue-100/30 rounded-full blur-3xl"
    ></div>
    <div
      class="absolute bottom-10 left-10 w-96 h-96 bg-purple-100/20 rounded-full blur-3xl"
    ></div>

    <!-- Section Header -->
    <div class="text-center mb-14 relative z-10">
      <div
        class="inline-flex items-center px-4 py-2 bg-white/80 backdrop-blur-sm border border-primary/20 text-secondary rounded-full text-sm font-semibold mb-4 shadow-sm"
      >
        <Icon name="heroicons:newspaper" class="w-4 h-4 mr-2" />
        সর্বশেষ নিবন্ধ
      </div>

      <h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-4">
        আমাদের সাম্প্রতিক
        <span
          class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
          >সংবাদ ও নিবন্ধ</span
        >
      </h2>
      <p
        class="text-lg md:text-xl text-gray-600 max-w-4xl mx-auto leading-relaxed"
      >
        বিশেষজ্ঞদের পরামর্শ, গাইড এবং রিভিউগুলো আবিষ্কার করুন, যা আপনাকে আপনার
        পরবর্তী গাড়ি সম্পর্কিত তথ্যভিত্তিক সিদ্ধান্ত নিতে সাহায্য করবে।
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
          <div class="h-[480px]">
            <BlogCard :blog="item" class="w-full h-full flex flex-col" />
          </div>
        </template>
      </UCarousel>
    </div>

    <!-- View All Articles Button -->
    <div class="text-center mt-12 relative z-10">
      <button
        class="px-8 py-4 bg-gradient-to-r from-primary to-secondary text-white rounded-full font-semibold hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex items-center justify-center gap-2 mx-auto"
      >
        <span>সব নিবন্ধ দেখুন</span>
        <Icon name="heroicons:arrow-right" class="text-lg" />
      </button>
    </div>
  </div>
</template>
