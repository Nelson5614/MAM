<template>
    <section id="services" class="py-20 bg-background">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 text-primary">
          Our Financial Solutions
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div 
            v-for="(service, index) in services" 
            :key="index"
            class="bg-white rounded-lg shadow-lg overflow-hidden"
          >
            <div class="p-6">
              <div class="flex items-center mb-4">
                <component :is="service.icon" class="w-16 h-16 text-secondary" />
                <h3 class="text-2xl font-semibold ml-4 text-primary">
                  {{ service.title }}
                </h3>
              </div>
              <p class="text-gray-600 mb-4">{{ service.description }}</p>
              <ul class="space-y-2 mb-6">
                <li 
                  v-for="(benefit, benefitIndex) in service.benefits" 
                  :key="benefitIndex"
                  class="flex items-start"
                >
                  <CheckCircleIcon class="w-5 h-5 text-secondary mr-2 flex-shrink-0" />
                  <span class="text-sm">{{ benefit }}</span>
                </li>
              </ul>
              <a
                href="#contact"
                class="inline-block w-full px-6 py-3 bg-secondary text-white rounded-full font-semibold text-center transition-colors hover:bg-primary"
              >
                {{ service.cta }}
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { 
    CurrencyDollarIcon, 
    BriefcaseIcon, 
    CheckCircleIcon 
  } from '@heroicons/vue/24/outline'
  
  const services = [
    {
      icon: CurrencyDollarIcon,
      title: 'Personal Loans',
      description: 'Flexible financing solutions to help you achieve your personal goals.',
      benefits: [
        'Competitive interest rates',
        'Flexible repayment terms',
        'Quick approval process',
        'No collateral required for qualified applicants'
      ],
      cta: 'Apply for a Personal Loan'
    },
    {
      icon: BriefcaseIcon,
      title: 'Small Business Loans',
      description: 'Empower your business growth with our tailored financial solutions.',
      benefits: [
        'Customized loan amounts',
        'Competitive interest rates',
        'Flexible repayment schedules',
        'Expert business advice and support'
      ],
      cta: 'Get a Business Loan Quote'
    }
  ]
  </script>
  
  <style scoped>
  /* Add any component-specific styles here if needed */
  </style>