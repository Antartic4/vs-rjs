<template>
    <nav class="navbar">
      <div class="navbar-container">
        <!-- Logo -->
        <div class="logo">
          <router-link to="/">
            <img :src="logo" alt="RJS Logo" class="logo-img" />
          </router-link>
        </div>
  
        <!-- Navigation Links -->
        <ul class="nav-links" :class="{ 'mobile-menu': isMobileMenuOpen }">
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/dashboard">Dashboard</router-link></li>
          <li><router-link to="/profile">Profile</router-link></li>
        </ul>
  
        <!-- Mobile Menu Button -->
        <button class="mobile-btn" @click="toggleMobileMenu">
          ☰
        </button>
      </div>
    </nav>
  </template>
  
  <script setup lang="ts">
  import { ref } from "vue";
  import logo from "../assets/logo-rjs.png";
  
  const isMobileMenuOpen = ref(false);
  
  const toggleMobileMenu = () => {
    isMobileMenuOpen.value = !isMobileMenuOpen.value;
  };
  </script>
  
  <style scoped>
  /* NAVBAR STYLING */
  .navbar {
    background: #333;
    color: white;
    padding: 15px 0;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 100;
  }
  
  /* Centering content */
  .navbar-container {
    max-width: 1200px; /* Set a max-width */
    margin: 0 auto; /* Center the navbar */
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px; /* Add padding */
  }
  
  /* Logo */
  .logo a {
    font-size: 1.8rem;
    font-weight: bold;
    text-decoration: none;
    color: white;
  }

  .logo-img {
    height: 50px;
    width: auto;
  }
  
  /* Navigation Links */
  .nav-links {
    display: flex;
    gap: 20px;
    list-style: none;
  }
  
  .nav-links a {
    text-decoration: none;
    color: white;
    font-size: 1.2rem;
    padding: 10px;
    transition: 0.3s;
  }
  
  .nav-links a:hover,
  .router-link-active {
    color: #ffcc00;
  }
  
  /* Mobile Menu Button */
  .mobile-btn {
    display: none;
    font-size: 1.8rem;
    background: none;
    border: none;
    color: white;
    cursor: pointer;
  }
  
  /* RESPONSIVE MOBILE MENU */
  @media (max-width: 768px) {
    .nav-links {
      display: none;
      flex-direction: column;
      background: #222;
      position: absolute;
      top: 60px;
      right: 20px;
      width: 200px;
      padding: 15px;
      border-radius: 5px;
    }
  
    .mobile-menu {
      display: flex;
    }
  
    .mobile-btn {
      display: block;
    }
  }
  </style>
  