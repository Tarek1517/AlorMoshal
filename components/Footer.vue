<template>
  <footer class="bg-gray-900 text-gray-300 pt-16 pb-10 mt-20">
    <div class="container mx-auto px-6 lg:px-12">
      <!-- Top Section -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-12 mb-12">
        <!-- Brand & About -->
        <div>
          <NuxtLink to="/" class="flex items-center group relative mb-8">
            <div class="flex items-center space-x-3">
              <div
                class="w-12 h-12 bg-primary rounded-xl flex items-center justify-center shadow-lg"
              >
                <Icon name="mdi:school" class="text-2xl text-white" />
              </div>
              <div class="flex flex-col">
                <span class="text-2xl font-bold text-white">
                  আলোর মশাল
                </span>
                <span class="text-xs text-gray-400 -mt-1"
                  >লএমএস প্ল্যাটফর্ম</span
                >
              </div>
            </div>
          </NuxtLink>
          <p class="text-gray-400 mb-6 leading-relaxed">
            আমরা মানসম্মত কোর্স, সহজ ব্যবহারযোগ্যতা ও শিক্ষার্থীদের সন্তুষ্টির
            মাধ্যমে শেখার জগতে নতুন পরিবর্তন আনছি।
          </p>
          <div class="flex gap-4">
            <a href="#"
              ><Icon name="logos:facebook" class="text-2xl hover:text-primary"
            /></a>
            <a href="#"
              ><Icon
                name="skill-icons:instagram"
                class="text-2xl hover:text-primary"
            /></a>
            <a href="#"
              ><Icon
                name="logos:youtube-icon"
                class="text-2xl hover:text-primary"
            /></a>
            <a href="#"
              ><Icon
                name="devicon:linkedin"
                class="text-2xl hover:text-primary"
            /></a>
          </div>
        </div>

        <!-- Quick Links -->
        <div class="grid grid-cols-2 gap-8">
          <div>
            <h3 class="text-white font-semibold text-lg mb-5">প্রতিষ্ঠান</h3>
            <ul class="space-y-3">
              <li>
                <NuxtLink to="/about" class="hover:text-primary"
                  >আমাদের সম্পর্কে</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/Extra/AppDownload" class="hover:text-primary"
                  >অ্যাপ ডাউনলোড</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/careers" class="hover:text-primary"
                  >ক্যারিয়ার</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/contact" class="hover:text-primary"
                  >যোগাযোগ</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/blog" class="hover:text-primary">ব্লগ</NuxtLink>
              </li>
            </ul>
          </div>

          <div>
            <h3 class="text-white font-semibold text-lg mb-5">সাপোর্ট</h3>
            <ul class="space-y-3">
              <li>
                <NuxtLink to="/faq" class="hover:text-primary"
                  >প্রশ্নোত্তর (FAQs)</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/shipping" class="hover:text-primary"
                  >ডেলিভারি</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/returns" class="hover:text-primary"
                  >ফেরত নীতি</NuxtLink
                >
              </li>
              <li>
                <NuxtLink to="/tracking" class="hover:text-primary"
                  >অর্ডার ট্র্যাকিং</NuxtLink
                >
              </li>
            </ul>
          </div>
        </div>

        <!-- নীতি ও নিউজলেটার -->
        <div>
          <h3 class="text-white font-semibold text-lg mb-5">নীতিমালা</h3>
          <ul class="space-y-3 mb-8">
            <li>
              <NuxtLink to="/terms" class="hover:text-primary"
                >সেবার শর্তাবলী</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/privacy" class="hover:text-primary"
                >গোপনীয়তা নীতি</NuxtLink
              >
            </li>
            <li>
              <NuxtLink to="/seller-terms" class="hover:text-primary"
                >বিক্রেতার শর্তাবলী</NuxtLink
              >
            </li>
          </ul>

          <!-- নিউজলেটার -->
          <h4 class="text-white font-medium mb-3">
            আমাদের নিউজলেটারে সাবস্ক্রাইব করুন
          </h4>
          <div class="flex gap-2">
            <input
              type="email"
              placeholder="আপনার ইমেল"
              class="bg-gray-800 border border-gray-700 rounded-lg px-4 py-2 text-sm text-gray-200 placeholder-gray-500 focus:ring-2 focus:ring-primary flex-grow"
            />
            <button
              class="bg-primary hover:bg-primary-dark text-white px-4 py-2 rounded-lg text-sm font-medium transition"
            >
              সাবস্ক্রাইব
            </button>
          </div>
        </div>
      </div>

      <!-- Divider -->
      <div class="border-t border-gray-700 my-8"></div>

      <!-- বটম সেকশন -->
      <div class="flex flex-col md:flex-row justify-between items-center gap-6">
        <!-- কপি -->
        <p class="text-gray-500 text-sm text-center md:text-left">
          &copy; 2025@আলোর মশাল. সর্বস্বত্ব সংরক্ষিত।
        </p>

        <!-- অ্যাপ ডাউনলোড ও পেমেন্ট -->
        <div class="flex flex-col sm:flex-row items-center gap-6">
          <!-- অ্যাপ ব্যাজ -->
          <div class="flex gap-3">
            <a href="#" class="bg-black p-2 rounded-lg hover:opacity-90">
              <img
                src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg"
                alt="Play Store"
                class="h-8"
              />
            </a>
            <a href="#" class="bg-black p-2 rounded-lg hover:opacity-90">
              <img
                src="https://developer.apple.com/assets/elements/badges/download-on-the-app-store.svg"
                alt="App Store"
                class="h-8"
              />
            </a>
          </div>

          <!-- পেমেন্ট আইকন -->
          <div class="flex gap-3">
            <span class="text-gray-500 text-sm">
              ডেভেলপ করেছে
              <a
                href="https://creativetechpark.com/"
                target="_blank"
                rel="noopener noreferrer"
                class="text-primary hover:text-primary-dark transition-colors duration-300"
              >
                Creative Tech Park
              </a>
            </span>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
// No script needed
</script>

<style scoped>
/* Smooth transitions for all interactive elements */
a,
button,
input {
  transition: all 0.2s ease;
}

/* Custom focus styles */
input:focus,
button:focus {
  outline: none;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.3);
}
</style>

<style scoped>
/* Smooth transitions for all interactive elements */
a,
button,
input {
  transition: all 0.2s ease;
}

/* Custom focus styles */
input:focus,
button:focus {
  outline: none;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.3);
}
</style>
