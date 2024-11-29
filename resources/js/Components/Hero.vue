<template>
    <section class="relative min-h-[calc(100vh-64px)] flex items-center justify-center bg-primary text-white overflow-hidden">
        <img
         src="https://images.unsplash.com/photo-1553877522-43269d4ea984?q=80&w=2070"
        alt="Modern financial technology"
        class="absolute inset-0 w-full h-full object-cover"
        />
        
        <div class="absolute inset-0 bg-gradient-to-b from-gray-900/90 to-gray-900/80"></div>
        
        <div class="relative z-10 text-center max-w-4xl px-4">
        <h1 class="text-4xl md:text-6xl font-bold mb-6" :class="animateClasses">
          Empowering Dreams Through Financial Inclusion
        </h1>
        
        <p class="text-xl md:text-2xl mb-8" :class="animateClasses">
          Access the resources you need to build a brighter financial future
        </p>
        
        <a
          href="#services"
          class="inline-flex items-center px-6 py-3 text-lg font-semibold bg-secondary text-white rounded-full transition-transform hover:scale-105"
          :class="animateClasses"
        >
          Explore Our Services
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5 ml-2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"
            />
          </svg>
        </a>
      </div>
    </section>
  </template>
  
  <script setup>
  const animateClasses = 'animate-fade-in-up'
  </script>
  
  <style scoped>
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .animate-fade-in-up {
    animation: fadeInUp 0.6s ease-out forwards;
  }
  
  /* Add animation delays for different elements */
  .animate-fade-in-up:nth-child(1) {
    animation-delay: 0ms;
  }
  
  .animate-fade-in-up:nth-child(2) {
    animation-delay: 200ms;
  }
  
  .animate-fade-in-up:nth-child(3) {
    animation-delay: 400ms;
  }
  </style>