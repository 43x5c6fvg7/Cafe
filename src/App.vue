<template>
  <div class="min-h-screen flex flex-col">
    <!-- Navbar -->
    <Navbar @toggleSidebar="sidebarOpen = true" />

    <!-- Sidebar -->
    <Sidebar :isOpen="sidebarOpen" @close="sidebarOpen = false" />

    <!-- Content -->
    <main class="flex-1 pt-20">
      <router-view />
    </main>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<script setup>
import { ref } from "vue"

// Import components (diqqat: .vue kengaytmasi bilan!)
import Navbar from "./Layouts/Navbar.vue"
import Footer from "./Layouts/Footer.vue"
import Sidebar from "./Layouts/Sidebar.vue"

const sidebarOpen = ref(false)
</script>

<style>
/* Optional: umumiy style */
body {
  margin: 0;
  font-family: system-ui, sans-serif;
}
</style>
