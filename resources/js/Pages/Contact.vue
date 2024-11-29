<template>
    <HomeLayout>
      <!-- Hero Section -->
      <div class="relative h-[400px] flex items-center justify-center">
        <!-- Background Image with Overlay -->
        <div 
          class="absolute inset-0"
          style="
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), 
            url('https://images.unsplash.com/photo-1560264280-88b68371db39?q=80&w=2070');
            background-size: cover;
            background-position: center;
          "
        ></div>

        <!-- Content -->
        <div class="relative z-10 text-center px-4 pt-16">
          <h1 class="text-4xl md:text-6xl font-bold mb-6 text-white">
            Contact Us
          </h1>
          <p class="text-xl md:text-2xl text-white">
            We're Here to Help You
          </p>
        </div>
      </div>
  
      <!-- Contact Section -->
      <section class="py-32 bg-gray-50">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
          <!-- Section Header -->
          <div class="text-center max-w-3xl mx-auto mb-20">
            <h2 class="text-3xl md:text-4xl font-bold text-primary mb-4">Get in Touch</h2>
            <p class="text-gray-600 text-lg">We're here to help and answer any questions you might have.</p>
          </div>

          <div class="grid grid-cols-1 lg:grid-cols-2 gap-20">
            
            <!-- Contact Form -->
            <div class="bg-white p-12 rounded-3xl shadow-xl">
              <h3 class="text-2xl font-bold text-primary mb-3">Send Us a Message</h3>
              <p class="text-gray-600 mb-10">Fill out the form and we'll get back to you as soon as possible.</p>
              
              <form @submit.prevent="submitForm" class="space-y-8">
                <!-- Name and Email Row -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                  <div class="space-y-3">
                    <label for="name" class="block text-sm font-medium text-gray-700">Full Name *</label>
                    <input
                      type="text"
                      id="name"
                      v-model="form.name"
                      class="w-full px-5 py-4 rounded-xl border border-gray-200 focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors"
                      required
                    />
                  </div>

                  <div class="space-y-3">
                    <label for="email" class="block text-sm font-medium text-gray-700">Email Address *</label>
                    <input
                      type="email"
                      id="email"
                      v-model="form.email"
                      class="w-full px-5 py-4 rounded-xl border border-gray-200 focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors"
                      required
                    />
                  </div>
                </div>

                <!-- Phone and Subject Row -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                  <div class="space-y-3">
                    <label for="phone" class="block text-sm font-medium text-gray-700">Phone Number</label>
                    <input
                      type="tel"
                      id="phone"
                      v-model="form.phone"
                      class="w-full px-5 py-4 rounded-xl border border-gray-200 focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors"
                    />
                  </div>

                  <div class="space-y-3">
                    <label for="subject" class="block text-sm font-medium text-gray-700">Subject *</label>
                    <input
                      type="text"
                      id="subject"
                      v-model="form.subject"
                      class="w-full px-5 py-4 rounded-xl border border-gray-200 focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors"
                      required
                    />
                  </div>
                </div>

                <!-- Message -->
                <div class="space-y-3">
                  <label for="message" class="block text-sm font-medium text-gray-700">Message *</label>
                  <textarea
                    id="message"
                    v-model="form.message"
                    rows="6"
                    class="w-full px-5 py-4 rounded-xl border border-gray-200 focus:ring-2 focus:ring-primary/20 focus:border-primary transition-colors resize-none"
                    required
                  ></textarea>
                </div>

                <!-- Submit Button -->
                <div class="pt-6">
                  <button
                    type="submit"
                    class="w-full bg-primary text-white py-4 px-8 rounded-xl font-semibold hover:bg-primary/90 transition-colors flex items-center justify-center space-x-3 text-lg"
                  >
                    <span>Send Message</span>
                    <PaperAirplaneIcon class="w-5 h-5" />
                  </button>
                </div>
              </form>
            </div>
  
            <!-- Contact Information -->
            <div class="lg:pl-12 space-y-12">
              <!-- Contact Cards -->
              <div class="space-y-8">
                <!-- Office Location -->
                <div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow">
                  <div class="flex items-start space-x-6">
                    <div class="p-4 bg-primary/10 rounded-xl">
                      <MapPinIcon class="w-8 h-8 text-primary" />
                    </div>
                    <div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2">Head Office</h3>
                      <p class="text-gray-600 text-lg leading-relaxed">
                        Mafeteng Reserve , <br>
                        Ntate Pitso's Building<br>
                        Next to IEC Office
                      </p>
                    </div>
                  </div>
                </div>
  
                <!-- Phone Numbers -->
                <div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow">
                  <div class="flex items-start space-x-6">
                    <div class="p-4 bg-primary/10 rounded-xl">
                      <PhoneIcon class="w-8 h-8 text-primary" />
                    </div>
                    <div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2">Phone Numbers</h3>
                      <div class="text-gray-600 text-lg space-y-1">
                        <p>(+266) 58030832 </p>
                        <p>(+266) 63036818</p>
                      </div>
                    </div>
                  </div>
                </div>
  
                <!-- Email -->
                <div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow">
                  <div class="flex items-start space-x-6">
                    <div class="p-4 bg-primary/10 rounded-xl">
                      <EnvelopeIcon class="w-8 h-8 text-primary" />
                    </div>
                    <div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2">Email Address</h3>
                      <p class="text-gray-600 text-lg">contact@mamfinancialservices.co.ls</p>
                    </div>
                  </div>
                </div>
  
                <!-- Business Hours -->
                <div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow">
                  <div class="flex items-start space-x-6">
                    <div class="p-4 bg-primary/10 rounded-xl">
                      <ClockIcon class="w-8 h-8 text-primary" />
                    </div>
                    <div>
                      <h3 class="font-semibold text-xl text-gray-900 mb-2">Business Hours</h3>
                      <div class="text-gray-600 text-lg space-y-1">
                        <p>Monday - Friday: 8:00 AM - 4:00 PM</p>
                        <p>Saturday: 9:00 AM - 1:00 PM</p>
                        <p>Sunday: Closed</p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
  
              <!-- Social Media Links -->
              <div class="mt-12 pt-12 border-t border-gray-200">
                <h3 class="font-semibold text-lg text-gray-900 mb-6">Follow Us</h3>
                <div class="flex space-x-6">
                  <a href="#" class="p-3 bg-primary/10 rounded-full hover:bg-primary/20 transition-colors">
                    <svg class="w-6 h-6 text-primary" fill="currentColor" viewBox="0 0 24 24">
                      <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                    </svg>
                  </a>
                  <a href="#" class="p-3 bg-primary/10 rounded-full hover:bg-primary/20 transition-colors">
                    <svg class="w-6 h-6 text-primary" fill="currentColor" viewBox="0 0 24 24">
                      <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
                    </svg>
                  </a>
                  <a href="#" class="p-3 bg-primary/10 rounded-full hover:bg-primary/20 transition-colors">
                    <svg class="w-6 h-6 text-primary" fill="currentColor" viewBox="0 0 24 24">
                      <path d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913.306.788.717 1.459 1.384 2.126.667.666 1.336 1.079 2.126 1.384.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558.788-.306 1.459-.718 2.126-1.384.666-.667 1.079-1.335 1.384-2.126.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913-.306-.789-.718-1.459-1.384-2.126C21.319 1.347 20.651.935 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227-.224.562-.479.96-.899 1.382-.419.419-.824.679-1.38.896-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421-.569-.224-.96-.479-1.379-.899-.421-.419-.69-.824-.9-1.38-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678c-3.405 0-6.162 2.76-6.162 6.162 0 3.405 2.76 6.162 6.162 6.162 3.405 0 6.162-2.76 6.162-6.162 0-3.405-2.76-6.162-6.162-6.162zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405c0 .795-.646 1.44-1.44 1.44-.795 0-1.44-.646-1.44-1.44 0-.794.646-1.439 1.44-1.439.793-.001 1.44.645 1.44 1.439z"/>
                    </svg>
                  </a>
                </div>
              </div>
            </div>
  
          </div>
        </div>
      </section>
    </HomeLayout>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  import HomeLayout from '@/Layouts/HomeLayout.vue'
  import { 
    MapPinIcon,
    EnvelopeIcon,
    PhoneIcon,
    ClockIcon,
    PaperAirplaneIcon
  } from '@heroicons/vue/24/outline'
  
  const form = ref({
    name: '',
    email: '',
    phone: '',
    subject: '',
    message: ''
  })
  
  const submitForm = () => {
    // Handle form submission
    console.log('Form submitted:', form.value)
  }
  </script>
  
  <style scoped>
  .animate-fade-in-up {
    opacity: 0;
    animation: fadeInUp 0.8s ease-out forwards;
  }
  
  .animation-delay-200 {
    animation-delay: 0.2s;
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
  </style>