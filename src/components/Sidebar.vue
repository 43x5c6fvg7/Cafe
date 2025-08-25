// components/Sidebar.vue
<template>
  <div v-if="isOpen" class="sidebar-overlay">
    <div class="sidebar-backdrop" @click="$emit('close')"></div>
    
    <aside class="sidebar">
      <!-- Header -->
      <div class="sidebar-header">
        <div class="sidebar-logo">
          <h3>Menu</h3>
        </div>
        <button class="close-btn" @click="$emit('close')">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <line x1="18" y1="6" x2="6" y2="18"></line>
            <line x1="6" y1="6" x2="18" y2="18"></line>
          </svg>
        </button>
      </div>

      <!-- Navigation -->
      <nav class="sidebar-nav">
        <div class="nav-section">
          <h4 class="nav-section-title">Main</h4>
          <ul class="nav-list">
            <li><a href="#" class="nav-link active">
              <svg class="nav-icon" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="m3 9 9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path>
                <polyline points="9,22 9,12 15,12 15,22"></polyline>
              </svg>
              Dashboard
            </a></li>
            <li><a href="#" class="nav-link">
              <svg class="nav-icon" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="m2 2 1 1h2l.4 2M7 13h10l4-8H5.4m0 0L7 13m0 0l-1.5 6M7 13l-1.5 6m0 0h9M17 13v6a2 2 0 01-2 2H9a2 2 0 01-2-2v-6"></path>
              </svg>
              Products
              <span class="nav-badge">New</span>
            </a></li>
            <li><a href="#" class="nav-link">
              <svg class="nav-icon" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"></path>
                <rect x="8" y="2" width="8" height="4" rx="1" ry="1"></rect>
              </svg>
              Orders
            </a></li>
          </ul>
        </div>

        <div class="nav-section">
          <h4 class="nav-section-title">Shop</h4>
          <ul class="nav-list">
            <li><a href="#" class="nav-link">
              <svg class="nav-icon" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path>
              </svg>
              Favorites
              <span class="nav-count">12</span>
            </a></li>
            <li><a href="#" class="nav-link">
              <svg class="nav-icon" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path>
                <circle cx="9" cy="7" r="4"></circle>
                <path d="m22 21-3-3m0-6a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path>
              </svg>
              Profile
            </a></li>
          </ul>
        </div>
      </nav>

      <!-- Footer -->
      <div class="sidebar-footer">
        <button class="sidebar-btn secondary">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <circle cx="12" cy="12" r="3"></circle>
            <path d="M12 1v6m0 12v6m11-7h-6m-12 0H1m15.5-6.5L19 6l-1.5-1.5M5 19l1.5-1.5M19 19l-1.5-1.5M5 5l1.5 1.5"></path>
          </svg>
          Settings
        </button>
        <button class="sidebar-btn danger">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M9 21H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h4"></path>
            <polyline points="16,17 21,12 16,7"></polyline>
            <line x1="21" y1="12" x2="9" y2="12"></line>
          </svg>
          Logout
        </button>
      </div>
    </aside>
  </div>
</template>

<script setup>
defineProps({
  isOpen: Boolean
})

defineEmits(['close'])
</script>

<style scoped>
.sidebar-overlay {
  position: fixed;
  inset: 0;
  z-index: 1100;
}

.sidebar-backdrop {
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(4px);
  animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.sidebar {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 280px;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(20px);
  border-right: 1px solid rgba(226, 232, 240, 0.8);
  display: flex;
  flex-direction: column;
  transform: translateX(-100%);
  animation: slideIn 0.3s ease forwards;
}

@keyframes slideIn {
  to { transform: translateX(0); }
}

.sidebar-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.5rem;
  border-bottom: 1px solid rgba(226, 232, 240, 0.8);
}

.sidebar-logo h3 {
  font-size: 1.25rem;
  font-weight: 700;
  color: #1e293b;
}

.close-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  background: none;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s ease;
  color: #64748b;
}

.close-btn:hover {
  background-color: #f1f5f9;
}

.sidebar-nav {
  flex: 1;
  padding: 1.5rem 0;
  overflow-y: auto;
}

.nav-section {
  margin-bottom: 2rem;
}

.nav-section-title {
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: #94a3b8;
  margin-bottom: 0.75rem;
  padding: 0 1.5rem;
}

.nav-list {
  list-style: none;
}

.nav-link {
  display: flex;
  align-items: center;
  padding: 0.75rem 1.5rem;
  color: #64748b;
  text-decoration: none;
  transition: all 0.2s ease;
  gap: 0.75rem;
  position: relative;
}

.nav-link:hover {
  background: rgba(102, 126, 234, 0.1);
  color: #667eea;
}

.nav-link.active {
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
  color: #667eea;
  font-weight: 600;
}

.nav-link.active::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 3px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.nav-icon {
  flex-shrink: 0;
}

.nav-badge {
  margin-left: auto;
  font-size: 0.75rem;
  font-weight: 600;
  background: #ef4444;
  color: white;
  padding: 0.125rem 0.5rem;
  border-radius: 999px;
}

.nav-count {
  margin-left: auto;
  font-size: 0.75rem;
  font-weight: 600;
  background: #e2e8f0;
  color: #64748b;
  padding: 0.125rem 0.5rem;
  border-radius: 999px;
}

.sidebar-footer {
  padding: 1.5rem;
  border-top: 1px solid rgba(226, 232, 240, 0.8);
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.sidebar-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.75rem;
  padding: 0.75rem 1rem;
  border: none;
  border-radius: 8px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s ease;
}

.sidebar-btn.secondary {
  background: #f1f5f9;
  color: #64748b;
}

.sidebar-btn.secondary:hover {
  background: #e2e8f0;
  transform: translateY(-1px);
}

.sidebar-btn.danger {
  background: rgba(239, 68, 68, 0.1);
  color: #ef4444;
}

.sidebar-btn.danger:hover {
  background: rgba(239, 68, 68, 0.2);
  transform: translateY(-1px);
}

@media (max-width: 768px) {
  .sidebar {
    width: 100%;
  }
}
</style>
