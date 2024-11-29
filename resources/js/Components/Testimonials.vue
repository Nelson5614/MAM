<template>
    <section class="py-20 bg-primary text-white">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl md:text-4xl font-bold text-center mb-12">
          Success Stories
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div 
            v-for="(testimonial, index) in testimonials" 
            :key="index"
            class="bg-white text-gray-800 p-6 rounded-lg shadow-md"
          >
            <p class="text-lg mb-4 italic">"{{ testimonial.quote }}"</p>
            <div class="flex items-center">
              <img
                :src="testimonial.image"
                :alt="testimonial.name"
                class="w-[60px] h-[60px] rounded-full mr-4 object-cover"
              />
              <div>
                <p class="font-semibold">{{ testimonial.name }}</p>
                <p class="text-gray-600">{{ testimonial.title }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  const testimonials = [
    {
      quote: "The microloan I received helped me expand my small business and provide for my family. I'm grateful for the opportunity and support.",
      name: "Maria Rodriguez",
      title: "Small Business Owner",
      image: "/testimonial-1.jpg"
    },
    {
      quote: "The financial education workshops gave me the knowledge and confidence to better manage my finances and plan for the future.",
      name: "John Doe",
      title: "Program Participant",
      image: "/testimonial-2.jpg"
    }
  ]
  </script>
  
  <style scoped>
  /* Optional: Add animations */
  .grid > div {
    transition: transform 0.3s ease;
  }
  
  .grid > div:hover {
    transform: translateY(-5px);
  }
  
  /* Optional: Add fade-in animation */
  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .grid > div {
    animation: fadeIn 0.6s ease-out forwards;
  }
  
  .grid > div:nth-child(2) {
    animation-delay: 0.2s;
  }
  </style>