<template>
    <div class="min-h-screen bg-gray-50">
      <!-- Navbar Component -->
      <Navbar />
      
      <!-- Main Content -->
      <main>
        <slot />
      </main>
  
      <!--Footer Component -->
      <Footer />
    </div>
  </template>
  
  <script setup>
  import Navbar from '@/Components/NavBar.vue'
  import Footer from '@/Components/Footer.vue'
  </script>