<template>
  <div>
    <!-- Overlay -->
    <div
      v-if="isOpen"
      class="fixed inset-0 bg-black bg-opacity-40 z-40"
      @click="closeSidebar"
    ></div>

    <!-- Sidebar -->
    <aside
      class="fixed top-0 left-0 h-full w-64 bg-white shadow-lg z-50 transform transition-transform duration-300"
      :class="isOpen ? 'translate-x-0' : '-translate-x-full'"
    >
      <div class="p-4 border-b flex justify-between items-center">
        <h2 class="text-xl font-bold">☰ Menu</h2>
        <button @click="closeSidebar" class="text-2xl">×</button>
      </div>

      <nav class="flex flex-col p-4 space-y-4">
        <router-link to="/" class="hover:text-red-500" @click="closeSidebar">Home</router-link>
        <router-link to="/menu" class="hover:text-red-500" @click="closeSidebar">Menu</router-link>
        <router-link to="/cart" class="hover:text-red-500" @click="closeSidebar">Cart</router-link>
        <router-link to="/profile" class="hover:text-red-500" @click="closeSidebar">Profile</router-link>
      </nav>
    </aside>
  </div>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  isOpen: Boolean,
});
const emit = defineEmits(["close"]);

const closeSidebar = () => {
  emit("close");
};
</script>
