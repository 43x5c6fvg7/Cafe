<template>
  <header class="bg-white shadow-md fixed top-0 left-0 right-0 z-50">
    <div class="container mx-auto flex justify-between items-center p-4">
      <!-- Logo -->
      <h1 class="text-2xl font-bold text-red-600">🍔 Scafe</h1>

      <!-- Menu (desktop) -->
      <nav class="hidden md:flex space-x-6">
        <router-link to="/" class="hover:text-red-500">Home</router-link>
        <router-link to="/menu" class="hover:text-red-500">Menu</router-link>
        <router-link to="/cart" class="hover:text-red-500">Cart</router-link>
        <router-link to="/profile" class="hover:text-red-500">Profile</router-link>
      </nav>

      <!-- Sidebar toggle (mobile) -->
      <button @click="$emit('toggleSidebar')" class="md:hidden text-2xl">
        ☰
      </button>
    </div>
  </header>
</template>
