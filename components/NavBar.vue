<script setup>
const activeMenu = ref(null);
const searchQuery = ref("");
const isLoggedIn = ref(false);
const currentLanguage = ref("EN");

const languages = [
  { code: "EN", name: "English" },
  { code: "BN", name: "বাংলা" },
  { code: "AR", name: "العربية" },
  { code: "ES", name: "Español" },
];

const menus = [
  {
    title: "Home",
    icon: "mdi:home",
    items: [],
  },
  {
    title: "Courses",
    items: [
      {
        title: "Web Development",
        icon: "mdi:web",
        subItems: [
          "Frontend",
          "Backend",
          "Full Stack",
          "React",
          "Vue",
          "Angular",
        ],
        image:
          "https://images.unsplash.com/photo-1627398242454-45a1465c2479?w=400&h=300&fit=crop",
      },
      {
        title: "Data Science",
        icon: "mdi:chart-bar",
        subItems: [
          "Python",
          "Machine Learning",
          "Deep Learning",
          "Data Analysis",
        ],
        image:
          "https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=400&h=300&fit=crop",
      },
      {
        title: "Mobile Development",
        icon: "mdi:cellphone",
        subItems: ["Android", "iOS", "Flutter", "React Native"],
        image:
          "https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?w=400&h=300&fit=crop",
      },
      {
        title: "Cloud & DevOps",
        icon: "mdi:cloud",
        subItems: ["AWS", "Docker", "Kubernetes", "CI/CD"],
        image:
          "https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=400&h=300&fit=crop",
      },
    ],
  },

  {
    title: "Resources",
    items: [
      {
        title: "Learning Paths",
        icon: "mdi:map-marker-path",
        subItems: ["Beginner to Pro", "Career Switch", "Skill Upgrade"],
      },
      {
        title: "Blog & Articles",
        icon: "mdi:book-open",
        subItems: ["Tutorials", "Industry News", "Study Guides"],
      },
      {
        title: "Community",
        icon: "mdi:account-group",
        subItems: ["Forums", "Study Groups", "Events"],
      },
      {
        title: "Support",
        icon: "mdi:help-circle",
        subItems: ["Help Center", "Technical Support", "FAQ"],
      },
    ],
  },
  {
    title: "About",
    items: [
      {
        title: "Our Story",
        icon: "mdi:history",
        subItems: ["Mission & Vision", "Team", "Achievements"],
      },
      {
        title: "Instructors",
        icon: "mdi:account-tie",
        subItems: ["Become Instructor", "Instructor Resources"],
      },
      {
        title: "Careers",
        icon: "mdi:briefcase",
        subItems: ["Open Positions", "Culture", "Benefits"],
      },
      {
        title: "Contact",
        icon: "mdi:phone",
        subItems: ["Support", "Partnerships", "Feedback"],
      },
    ],
  },
];
</script>

<template>
  <header
    class="sticky top-0 z-50 bg-white/95 backdrop-blur-md border-b border-gray-100 shadow-lg"
  >
    <div class="container mx-auto">
      <div class="flex items-center justify-between h-20">
        <!-- Logo -->
        <NuxtLink to="/" class="flex items-center group relative">
          <div class="flex items-center space-x-3">
            <div
              class="w-12 h-12 bg-primary rounded-xl flex items-center justify-center shadow-lg"
            >
              <Icon name="mdi:school" class="text-2xl text-secondary" />
            </div>
            <div class="flex flex-col">
              <span
                class="text-2xl font-bold bg-primary bg-clip-text text-transparent"
              >
                Alormoshal
              </span>
              <span class="text-xs text-secondary -mt-1">LMS Platform</span>
            </div>
          </div>
        </NuxtLink>

        <!-- Desktop Menu - Centered with Gap -->
        <nav class="hidden lg:flex items-center">
          <div
            v-for="(menu, index) in menus"
            :key="index"
            @mouseenter="activeMenu = index"
            @mouseleave="activeMenu = null"
            class="relative"
          >
            <!-- Home Button (Simple Link) -->
            <NuxtLink
              v-if="menu.title === 'Home'"
              to="/"
              class="px-6 py-3 text-gray-700 font-semibold hover:text-blue-600 transition-all duration-300 flex items-center group relative"
            >
              <Icon
                :name="menu.icon"
                class="mr-2 text-lg text-secondary group-hover:text-blue-600 transition-colors"
              />
              <span class="relative z-10">{{ menu.title }}</span>
              
            </NuxtLink>

            <!-- Other Menu Items (With Dropdown) -->
            <button
              v-else
              class="px-6 py-3 text-gray-700 font-semibold hover:text-blue-600 transition-all duration-300 flex items-center group relative"
            >
              <span class="relative z-10">{{ menu.title }}</span>
             
              <Icon
                name="mdi:chevron-down"
                class="ml-2 text-gray-400 text-lg transition-transform duration-200 group-hover:rotate-180 group-hover:text-blue-600"
              />
            </button>

          </div>
        </nav>

        <!-- Right Side Actions -->
        <div class="flex items-center">
          <!-- Search Bar -->
          <div class="relative hidden md:block">
            <div class="relative group">
              <input
                v-model="searchQuery"
                type="text"
                placeholder="Search courses, tutorials..."
                class="pl-12 pr-5 py-3 border-0 bg-gray-50 rounded-full focus:ring-2 focus:ring-blue-500/50 focus:bg-white w-64 transition-all duration-300 group-hover:w-72 focus:w-72 shadow-inner"
              />
              <div
                class="absolute inset-y-0 left-0 flex items-center pl-4 pointer-events-none"
              >
                <Icon
                  name="mdi:magnify"
                  class="text-xl text-gray-500 group-hover:text-blue-600 transition-colors"
                />
              </div>
              <button
                v-if="searchQuery"
                @click="searchQuery = ''"
                class="absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400 hover:text-blue-600 transition-colors"
              >
                <Icon name="mdi:close" class="text-lg" />
              </button>
            </div>
          </div>

          <!-- Language Selector -->
          <div class="relative group">
            <button
              class="flex items-center space-x-2 px-3 py-2 text-gray-600 hover:text-blue-600 transition-colors rounded-lg hover:bg-gray-50"
            >
              <Icon name="mdi:translate" class="text-lg" />
              <span class="font-medium">{{ currentLanguage }}</span>
              <Icon name="mdi:chevron-down" class="text-gray-400" />
            </button>
            <div
              class="absolute right-0 mt-2 w-48 bg-white rounded-xl shadow-2xl border border-gray-200 opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-200 z-50"
            >
              <div class="py-2">
                <button
                  v-for="lang in languages"
                  :key="lang.code"
                  @click="currentLanguage = lang.code"
                  class="w-full px-4 py-3 text-left hover:bg-blue-50 transition-colors flex items-center justify-between"
                  :class="{
                    'text-blue-600 bg-blue-50': currentLanguage === lang.code,
                  }"
                >
                  <span>{{ lang.name }}</span>
                  <Icon
                    v-if="currentLanguage === lang.code"
                    name="mdi:check"
                    class="text-blue-600"
                  />
                </button>
              </div>
            </div>
          </div>

          <!-- Auth Buttons -->
          <div class="flex items-center space-x-3" v-if="!isLoggedIn">
            <NuxtLink
              to="/login"
              class="px-6 py-2.5 text-white font-semibold bg-primary transition-colors rounded-full "
            >
              Login
            </NuxtLink>
            <NuxtLink
              to="/register"
              class="px-6 py-2.5 text-white font-semibold bg-secondary transition-colors rounded-full "
            >
              Register
            </NuxtLink>
          </div>

          <!-- User Menu (when logged in) -->
          <div class="flex items-center space-x-3" v-else>
            <NuxtLink
              to="/my-courses"
              class="p-2 text-gray-600 hover:text-blue-600 transition-colors"
            >
              <Icon name="mdi:bookmark" class="text-2xl" />
            </NuxtLink>
            <NuxtLink
              to="/notifications"
              class="p-2 text-gray-600 hover:text-blue-600 transition-colors relative"
            >
              <Icon name="mdi:bell" class="text-2xl" />
              <span
                class="absolute top-1 right-1 w-2 h-2 bg-red-500 rounded-full"
              ></span>
            </NuxtLink>
            <div class="relative group">
              <button
                class="flex items-center space-x-3 p-2 rounded-xl hover:bg-gray-50 transition-colors"
              >
                <div
                  class="w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-500 rounded-full flex items-center justify-center"
                >
                  <span class="text-white font-semibold">JD</span>
                </div>
              </button>
            </div>
          </div>

          <!-- Mobile Menu Toggle -->
          <button
            class="lg:hidden p-3 rounded-xl bg-gray-50 hover:bg-gray-100 transition-colors"
          >
            <Icon name="mdi:menu" class="text-2xl text-gray-700" />
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.mega-menu-enter-active,
.mega-menu-leave-active {
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
.mega-menu-enter-from,
.mega-menu-leave-to {
  opacity: 0;
  transform: translateY(-15px) scale(0.95);
}

.dropdown-enter-active,
.dropdown-leave-active {
  transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}
.dropdown-enter-from,
.dropdown-leave-to {
  opacity: 0;
  transform: translateY(-10px) translateX(-50%);
}

.line-clamp-1 {
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
</style>
