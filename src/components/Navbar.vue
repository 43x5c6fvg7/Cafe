// components/Navbar.vue
<template>
  <nav class="navbar">
    <div class="navbar-container">
      <!-- Left side -->
      <div class="navbar-left">
        <button class="sidebar-toggle" @click="$emit('toggle-sidebar')">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <line x1="3" y1="6" x2="21" y2="6"></line>
            <line x1="3" y1="12" x2="21" y2="12"></line>
            <line x1="3" y1="18" x2="21" y2="18"></line>
          </svg>
        </button>
        
        <div class="logo">
          <h2>ShopHub</h2>
        </div>
      </div>

      <!-- Center -->
      <div class="navbar-center">
        <div class="search-bar">
          <svg class="search-icon" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <circle cx="11" cy="11" r="8"></circle>
            <path d="m21 21-4.35-4.35"></path>
          </svg>
          <input type="text" placeholder="Search products...">
        </div>
      </div>

      <!-- Right side -->
      <div class="navbar-right">
        <button class="nav-btn cart-btn">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="m2 2 1 1h2l.4 2M7 13h10l4-8H5.4m0 0L7 13m0 0l-1.5 6M7 13l-1.5 6m0 0h9M17 13v6a2 2 0 01-2 2H9a2 2 0 01-2-2v-6"></path>
          </svg>
          <span class="cart-count">3</span>
        </button>
        
        <button class="nav-btn">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.29 1.51 4.04 3 5.5l11 11Z"></path>
          </svg>
        </button>

        <div class="user-menu">
          <button class="user-avatar">
            <img src="https://via.placeholder.com/32x32/667eea/ffffff?text=U" alt="User" />
          </button>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
defineEmits(['toggle-sidebar'])
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 70px;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(226, 232, 240, 0.8);
  z-index: 1000;
}

.navbar-container {
  height: 100%;
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 1.5rem;
}

.navbar-left {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.sidebar-toggle {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: none;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s ease;
  color: #64748b;
}

.sidebar-toggle:hover {
  background-color: #f1f5f9;
}

.logo h2 {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-size: 1.5rem;
  font-weight: 700;
}

.navbar-center {
  flex: 1;
  max-width: 500px;
  margin: 0 2rem;
}

.search-bar {
  position: relative;
  width: 100%;
}

.search-icon {
  position: absolute;
  left: 12px;
  top: 50%;
  transform: translateY(-50%);
  color: #94a3b8;
}

.search-bar input {
  width: 100%;
  height: 44px;
  padding: 0 16px 0 44px;
  border: 2px solid #e2e8f0;
  border-radius: 22px;
  font-size: 14px;
  background: #ffffff;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.search-bar input:focus {
  outline: none;
  border-color: #667eea;
  box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
}

.navbar-right {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.nav-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 44px;
  height: 44px;
  background: none;
  border: none;
  border-radius: 12px;
  cursor: pointer;
  transition: background-color 0.2s ease, transform 0.2s ease;
  color: #64748b;
  position: relative;
}

.nav-btn:hover {
  background-color: #f1f5f9;
  transform: translateY(-1px);
}

.cart-count {
  position: absolute;
  top: -8px;
  right: -8px;
  background: #ef4444;
  color: white;
  font-size: 12px;
  font-weight: 600;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.user-avatar {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  border: 2px solid #e2e8f0;
  background: none;
  cursor: pointer;
  overflow: hidden;
  transition: border-color 0.2s ease;
}

.user-avatar:hover {
  border-color: #667eea;
}

.user-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media (max-width: 768px) {
  .navbar-center {
    display: none;
  }
  
  .navbar-container {
    padding: 0 1rem;
  }
  
  .navbar-right {
    gap: 0.5rem;
  }
}
</style>