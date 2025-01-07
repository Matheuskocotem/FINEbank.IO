<template>
  <nav class="navigation-sidebar" role="navigation" aria-label="Main navigation">
    <div class="brand-container">
      <h1 class="brand-name">
        <span class="brand-name-bold">FINE</span>
        <span class="brand-name-regular">bank.</span>
        <span class="brand-name-bold">IO</span>
      </h1>
    </div>
    <div class="navigation-menu">
      <button 
        v-for="(item, index) in menuItems" 
        :key="index"
        :class="['menu-item', { active: item.isActive }]"
        @click="handleMenuClick(item.id)"
        :aria-label="item.label"
        tabindex="0"
      >
        <img
          :src="item.icon"
          :alt="item.label"
          class="menu-icon"
          aria-hidden="true"
        />
        <span class="menu-text">{{ item.label }}</span>
      </button>
    </div>
    <div class="navigation-footer">
      <button 
        class="logout-button"
        @click="handleLogout"
        aria-label="Logout"
        tabindex="0"
      >
        <img
          src="https://cdn.builder.io/api/v1/image/assets/TEMP/4831dc923e80e3ec0af5d5478c7a226d97c1ff9dca8504ba6b6a109fe36b87e0?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779"
          alt=""
          class="logout-icon"
          aria-hidden="true"
        />
        <span class="logout-text">Logout</span>
      </button>
      <div class="profile-section">
        <div class="profile-content">
          <img
            src="https://cdn.builder.io/api/v1/image/assets/TEMP/1d4b723ef6e0719e201adad107cadb697be0e8d01f2777b699f78a77c4a93f1d?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779"
            alt="Profile picture of Tanzir Rahman"
            class="profile-image"
          />
          <div class="profile-info">
            <span class="profile-name">Tanzir Rahman</span>
            <button 
              class="profile-link"
              @click="handleViewProfile"
              tabindex="0"
            >
              View profile
            </button>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

interface MenuItem {
  id: string;
  label: string;
  icon: string;
  isActive: boolean;
}

export default defineComponent({
  name: 'NavigationBar',
  data() {
    return {
      menuItems: [
        { id: 'overview', label: 'Overview', icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/dce81fa67e1dc14a78fd76ced1453944c0bbbc4394516313a350a4f245b2efbd?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779', isActive: true },
        { id: 'balances', label: 'Balances', icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/520b77053fccc079fd2f968bbc8a3a0227aa215f7339329e95999e35573e3398?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779', isActive: false },
        { id: 'transactions', label: 'Transactions', icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/d26022b20430060841be994861a4788647f0faf8c01ac7234840911c59699f72?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779', isActive: false },
        { id: 'bills', label: 'Bills', icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/a637e2a053ae0589e5d6582b5c00f9011882466648149c14644342c25cdb5b38?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779', isActive: false },
        { id: 'expenses', label: 'Expenses', icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/85f2a5d0aded8feb19ea22afc32cc8d680aceb435fe48415076f29289fce6c72?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779', isActive: false },
        { id: 'goals', label: 'Goals', icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/99a22f7c6093d10b501fe74e943d25e0c0961d6e7cdf2dafbea9377b5894bd9c?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779', isActive: false },
        { id: 'settings', label: 'Settings', icon: 'https://cdn.builder.io/api/v1/image/assets/TEMP/d6e86405b57b5753ae20cfa5c86f1afc6707c78a458e7efbbe9223e29e642ac5?placeholderIfAbsent=true&apiKey=0a461fa91b5e46398964470fbb62d779', isActive: false },
      ] as MenuItem[]
    }
  },
  methods: {
    handleMenuClick(id: string): void {
      this.menuItems = this.menuItems.map(item => ({
        ...item,
        isActive: item.id === id
      }))
    },
    handleLogout(): void {
      // Implement logout logic
    },
    handleViewProfile(): void {
      // Implement profile view logic
    }
  }
})
</script>

<style scoped>
.navigation-sidebar {
  background: var(--Default-Black, #191919);
  display: flex;
  max-width: 280px;
  flex-direction: column;
  padding: 48px 28px;
}

.brand-container {
  margin-bottom: 40px;
}

.brand-name {
  color: var(--White, #fff);
  text-align: center;
  letter-spacing: 1.92px;
  font: 500 24px/1 Poppins, sans-serif;
}

.brand-name-bold {
  font-weight: 800;
}

.brand-name-regular {
  font-weight: 500;
}

.navigation-menu {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.menu-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px 16px;
  border-radius: 4px;
  border: none;
  background: transparent;
  color: var(--Special-BG2, rgba(255, 255, 255, 0.7));
  font: 400 16px Inter, sans-serif;
  cursor: pointer;
  width: 100%;
  text-align: left;
}

.menu-item.active {
  background: var(--Primary-color, #299d91);
  color: var(--White, #fff);
  font-weight: 600;
}

.menu-icon {
  width: 24px;
  height: 24px;
  object-fit: contain;
}

.navigation-footer {
  margin-top: auto;
  padding-top: 44px;
}

.logout-button {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px 16px;
  border-radius: 4px;
  background: var(--Special-BG3, rgba(255, 255, 255, 0.08));
  opacity: 0.75;
  border: none;
  cursor: pointer;
  width: 100%;
}

.logout-icon {
  width: 20px;
  height: 20px;
  object-fit: contain;
}

.logout-text {
  color: var(--White, #fff);
  font: 600 16px Inter, sans-serif;
}

.profile-section {
  border-top: 1px solid var(--Special-BG3, rgba(255, 255, 255, 0.08));
  margin-top: 44px;
  padding: 32px 0;
}

.profile-content {
  display: flex;
  align-items: center;
  gap: 16px;
}

.profile-image {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  object-fit: contain;
}

.profile-info {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.profile-name {
  color: var(--White, #fff);
  font: 600 16px Inter, sans-serif;
}

.profile-link {
  color: var(--Special-BG2, rgba(255, 255, 255, 0.7));
  font: 400 12px Inter, sans-serif;
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  text-align: left;
}
</style>