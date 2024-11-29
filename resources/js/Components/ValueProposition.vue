<template>
    <section class="py-20 bg-background">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 text-primary">Why Choose Us</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-6 gap-8">
          <!-- Existing Cards -->
          <div 
            v-for="(value, index) in values.slice(0, 3)" 
            :key="index"
            class="bg-white p-6 rounded-lg shadow-md transition-transform hover:scale-105 lg:col-span-2"
          >
            <div class="flex justify-center mb-4">
              <component :is="value.icon" class="w-12 h-12 text-secondary" />
            </div>
            <h3 class="text-xl font-semibold mb-2 text-center text-primary">{{ value.title }}</h3>
            <p class="text-gray-600 text-center">{{ value.description }}</p>
          </div>
  
          <!-- New Cards -->
          <div 
            v-for="(value, index) in values.slice(3)" 
            :key="index + 3"
            class="bg-white p-6 rounded-lg shadow-md transition-transform hover:scale-105 lg:col-span-2"
          >
            <div class="flex justify-center mb-4">
              <component :is="value.icon" class="w-12 h-12 text-secondary" />
            </div>
            <h3 class="text-xl font-semibold mb-2 text-center text-primary">{{ value.title }}</h3>
            <p class="text-gray-600 text-center">{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { 
    LightBulbIcon, 
    ScaleIcon, 
    UserGroupIcon,
    BoltIcon,
    DocumentTextIcon,
    CheckCircleIcon
  } from '@heroicons/vue/24/outline'
  
  const values = [
    {
      icon: LightBulbIcon,
      title: 'Innovative Solutions',
      description: 'Tailored financial products designed to meet your unique needs and goals.'
    },
    {
      icon: ScaleIcon,
      title: 'Fair & Transparent',
      description: 'Clear terms, competitive rates, and no hidden fees. Your trust is our priority.'
    },
    {
      icon: UserGroupIcon,
      title: 'Community Impact',
      description: 'By empowering individuals, we strengthen entire communities.'
    },
    {
      icon: BoltIcon,
      title: 'Fast Approval',
      description: 'Quick decision-making process with minimal waiting time for loan approvals.'
    },
    {
      icon: DocumentTextIcon,
      title: 'Easy Documentation',
      description: 'Simple and straightforward documentation requirements with guided assistance.'
    },
    {
      icon: CheckCircleIcon,
      title: 'Hassle-Free Process',
      description: 'Streamlined application process with dedicated support at every step.'
    }
  ]
  </script>
  
  <style scoped>
  /* Add staggered animation for cards */
  .grid > div {
    animation: fadeInUp 0.5s ease-out forwards;
    opacity: 0;
  }
  
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
  
  /* Stagger the animations */
  .grid > div:nth-child(1) { animation-delay: 0.1s; }
  .grid > div:nth-child(2) { animation-delay: 0.2s; }
  .grid > div:nth-child(3) { animation-delay: 0.3s; }
  .grid > div:nth-child(4) { animation-delay: 0.4s; }
  .grid > div:nth-child(5) { animation-delay: 0.5s; }
  .grid > div:nth-child(6) { animation-delay: 0.6s; }
  
  /* Add hover effect for cards */
  .grid > div {
    transition: all 0.3s ease;
  }
  
  .grid > div:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  }
  </style>