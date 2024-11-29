<template>
    <section class="py-20 bg-white">
      <div class="container mx-auto px-4">
        <h2 class="text-4xl md:text-5xl font-bold text-center mb-16 text-primary">
          Frequently Asked Questions
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-start max-w-6xl mx-auto">
          <!-- Image Section -->
          <div class="relative h-[600px] rounded-lg overflow-hidden">
            <img
              src="/images/faq.png"
              alt="Customer service representative"
              class="absolute inset-0 w-full h-full object-cover rounded-lg"
            />
          </div>
  
          <!-- Accordion Section -->
          <div class="space-y-4">
            <div v-for="(faq, index) in faqs" :key="index">
              <div class="border rounded-lg">
                <button
                  class="w-full px-4 py-4 text-left text-lg font-semibold text-primary flex justify-between items-center"
                  @click="toggleAccordion(index)"
                >
                  {{ faq.question }}
                  <svg
                    class="w-6 h-6 transform transition-transform"
                    :class="{ 'rotate-180': activeIndex === index }"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M19 9l-7 7-7-7"
                    />
                  </svg>
                </button>
                <div
                  v-show="activeIndex === index"
                  class="px-4 pb-4 text-text"
                  :class="{ 'animate-fade-in': activeIndex === index }"
                >
                  {{ faq.answer }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const activeIndex = ref(null)
  
  const faqs = [
    {
      question: "How do I sign up for an account?",
      answer: "Signing up is easy! Visit our registration page and follow the simple steps to create your account. You'll need to provide some basic information and verify your identity to get started."
    },
    {
      question: "How secure is my information with Sinza?",
      answer: "We take security seriously. All your data is encrypted using industry-standard protocols, and we employ multiple layers of security measures to protect your personal and financial information."
    },
    {
      question: "Can I transfer funds to accounts outside of this bank?",
      answer: "Yes, you can transfer funds to external accounts. We support both domestic and international transfers, with competitive rates and secure transaction processing."
    },
    {
      question: "Can I set up personalized alerts for my account?",
      answer: "Yes, you can customize alerts for various account activities including deposits, withdrawals, low balance notifications, and suspicious activity alerts through your account settings."
    }
  ]
  
  const toggleAccordion = (index) => {
    activeIndex.value = activeIndex.value === index ? null : index
  }
  </script>
  
  <style scoped>
  .animate-fade-in {
    animation: fadeIn 0.3s ease-in-out;
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(-10px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  /* Smooth transition for accordion */
  div[v-show] {
    transition: all 0.3s ease-in-out;
  }
  
  /* Optional: Add hover effect to accordion items */
  button:hover {
    background-color: rgba(0, 0, 0, 0.02);
  }
  </style>