<script setup>
import { ref } from 'vue';

const isDropdownOpen = ref(false);

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value;
};
</script>

<template>
  <div class="menu-container">
    <div class="menu-item">
      <img src="../assets/tradeview-logo.png" alt="Logo" class="logo">
    </div>
    <div class="menu-item">
      <ul class="menu-list">
        <li><a href="#" class="menu-link">Forex</a></li>
        <li><a href="#" class="menu-link">Stocks</a></li>
        <li><a href="#" class="menu-link">Futures</a></li>
        <li><a href="#" class="menu-link">TradeGATEHub</a></li>
      </ul>
    </div>
    <div class="menu-item">
      <a href="#" class="menu-link">Login</a>
      <div class="dropdown">
        <a href="#" class="menu-link" @click="toggleDropdown">Contact Us</a>
        <div v-if="isDropdownOpen" class="dropdown-content">
          <a href="#" class="dropdown-link">Option 1</a>
          <a href="#" class="dropdown-link">Option 2</a>
          <a href="#" class="dropdown-link">Option 3</a>
        </div>
      </div>
      <a href="#" class="menu-link">English</a>
    </div>
  </div>
</template>

<style scoped>
.menu-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #333;
  color: #fff;
  padding: 10px;
}

.menu-item {
  display: flex;
  align-items: center;
}

.logo {
  width: 50px;
  height: 50px;
}

.menu-list {
  list-style: none;
  display: flex;
  gap: 10px;
}

.menu-link, .dropdown-link {
  text-decoration: none;
  color: #fff;
  transition: color 0.3s;
}

.menu-link:hover, .dropdown-link:hover {
  color: #ccc;
}

.dropdown {
  position: relative;
  display: inline-block;
  margin-left: 20px;
}

.dropdown-content {
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  padding: 10px;
  display: none;
}

.dropdown-link {
  display: block;
  padding: 5px 0;
  color: #333;
  text-decoration: none;
}

.dropdown-link:hover {
  background-color: #f1f1f1;
}
</style>
