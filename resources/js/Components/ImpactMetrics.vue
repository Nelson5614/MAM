<template>
    <section class="py-20 bg-background">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 text-primary">
          Our Impact
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div 
            v-for="(metric, index) in metrics" 
            :key="index" 
            class="text-center"
          >
            <div class="flex justify-center mb-4">
              <component :is="metric.icon" class="w-12 h-12 text-secondary" />
            </div>
            <p class="text-4xl font-bold mb-2 text-primary">{{ metric.value }}</p>
            <p class="text-xl text-gray-600">{{ metric.label }}</p>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { 
    UsersIcon, 
    CurrencyDollarIcon, 
    GlobeAltIcon 
  } from '@heroicons/vue/24/outline'
  
  const metrics = [
    {
      icon: UsersIcon,
      value: "50,000+",
      label: "Lives Impacted"
    },
    {
      icon: CurrencyDollarIcon,
      value: "$10M+",
      label: "in Microloans Disbursed"
    },
    {
      icon: GlobeAltIcon,
      value: "20+",
      label: "Countries Served"
    }
  ]
  </script>
  
  <style scoped>
  /* Optional: Add animation for numbers */
  @keyframes countUp {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .text-4xl {
    animation: countUp 1s ease-out forwards;
  }
  </style>