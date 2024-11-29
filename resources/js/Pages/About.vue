<template>
    <HomeLayout>
        
        <!-- Hero Section -->
        <section class="relative pt-24 md:pt-32 min-h-screen flex items-center justify-center bg-primary text-white overflow-hidden">
            <!-- Background Image -->
            <img
                src="https://images.unsplash.com/photo-1573164713714-d95e436ab8d6?q=80&w=2069"
                alt="Team collaboration"
                class="absolute inset-0 w-full h-full object-cover object-center"
            />
            
            <!-- Single, Stronger Overlay -->
            <div 
                class="absolute inset-0 bg-black opacity-75"
                style="background: linear-gradient(to bottom, rgba(0,0,0,0.85), rgba(0,0,0,0.75));"
            ></div>
            
            <!-- Content -->
            <div class="relative z-20 text-center max-w-4xl px-4">
                <h1 class="text-4xl md:text-6xl font-bold mb-6 animate-fade-in-up text-white">
                About M.A.M Financial Services
                </h1>
                <p class="text-xl md:text-2xl animate-fade-in-up animation-delay-200 text-gray-100">
                Building Financial Futures Together
                </p>
            </div>
        </section>
    
        <!-- Mission & Vision Section -->
        <section class="py-32 mt-20 bg-white relative z-10">
            <div class="max-w-7xl mt-12 mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-12">
                    <!-- Mission Card -->
                    <div class="bg-white p-4 lg:p-12 rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300">
                        <div class="flex flex-col sm:flex-row items-start sm:items-center gap-4 mb-8">
                            <div class="p-4 bg-primary/10 rounded-full">
                                <FlagIcon class="w-8 h-8 text-primary" />
                            </div>
                            <h2 class="text-2xl lg:text-3xl font-bold text-primary">Our Mission</h2>
                        </div>
                        <div class="space-y-4">
                            <p class="text-base lg:text-lg text-gray-600 leading-relaxed p-4">
                                We strive to provide financial peace of mind by helping our clients achieve their financial goals as well as understanding each of our clients unique purpose.
                            </p>
                        </div>
                    </div>

                    <!-- Vision Card -->
                    <div class="bg-white p-8 lg:p-12 rounded-2xl shadow-lg hover:shadow-xl transition-all duration-300">
                        <div class="flex flex-col sm:flex-row items-start sm:items-center gap-4 mb-8">
                            <div class="p-4 bg-primary/10 rounded-full">
                                <EyeIcon class="w-8 h-8 text-primary" />
                            </div>
                            <h2 class="text-2xl lg:text-3xl font-bold text-primary">Our Vision</h2>
                        </div>
                        <div class="space-y-2">
                            <p class="text-base lg:text-lg text-gray-600 leading-relaxed p-4">
                                To work with dedication and transparency to achieve excellence in service delivery, reliability and customer care as the ultimate goal. Also to earn the trust and confidence of our stakeholders, exceeding their expectations and making MAM Financial Services a respected and leading micro finance company.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    
        <!-- Core Values Section -->
        <section class="py-20 bg-background">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl md:text-4xl font-bold text-center mb-12 text-primary">Our Core Values</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-5 gap-8">
            <div v-for="(value, index) in coreValues" :key="index"
                class="bg-white p-6 rounded-lg shadow-md transition-all duration-300 hover:shadow-xl">
                <div class="flex justify-center mb-4">
                <component :is="value.icon" class="w-12 h-12 text-secondary" />
                </div>
                <h3 class="text-xl font-semibold mb-2 text-center text-primary">{{ value.title }}</h3>
                <p class="text-gray-600 text-center">{{ value.description }}</p>
            </div>
            </div>
        </div>
        </section>
    
      
    
        <!-- Stats Section -->
        <section class="py-20 bg-primary text-white">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
            <div v-for="(stat, index) in stats" :key="index" class="text-center">
                <div class="text-4xl font-bold mb-2">{{ stat.value }}</div>
                <div class="text-lg opacity-80">{{ stat.label }}</div>
            </div>
            </div>
        </div>
        </section>
    
        <!-- CTA Section -->
        <section class="py-20 bg-white">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl md:text-4xl font-bold mb-6 text-primary">Ready to Get Started?</h2>
            <p class="text-gray-600 mb-8 max-w-2xl mx-auto">
            Join thousands of satisfied clients who have trusted M.A.M Financial Services with their financial needs.
            </p>
            <Link
            :href="route('contact')"
            class="inline-flex items-center px-6 py-3 text-lg font-semibold bg-secondary text-white rounded-full transition-transform hover:scale-105"
            >
            Contact Us Today
            <ArrowRightIcon class="w-5 h-5 ml-2" />
            </Link>
        </div>
        </section>
        
    </HomeLayout>
  </template>
  
  <script setup>
  import { Link } from '@inertiajs/vue3'
  import HomeLayout from '@/Layouts/HomeLayout.vue'
  import { 
  FlagIcon, // Replacing TargetIcon
  EyeIcon, 
  StarIcon,
  CheckBadgeIcon,
  BriefcaseIcon,
  LightBulbIcon,
  AcademicCapIcon,
  ArrowRightIcon 
} from '@heroicons/vue/24/outline'

  
  const coreValues = [
    {
      icon: StarIcon,
      title: 'Excellence',
      description: 'Striving for the highest standards in everything we do to deliver exceptional service.'
    },
    {
      icon: CheckBadgeIcon,
      title: 'Quality',
      description: 'Maintaining superior standards in our services and customer relationships.'
    },
    {
      icon: BriefcaseIcon,
      title: 'Professionalism',
      description: 'Upholding the highest level of professional conduct and ethical standards.'
    },
    {
      icon: LightBulbIcon,
      title: 'Innovation',
      description: 'Embracing new ideas and technologies to improve our services continuously.'
    },
    {
      icon: AcademicCapIcon,
      title: 'Continuous Learning',
      description: 'Committed to growth and development through ongoing education and improvement.'
    }
  ]
  
  const teamMembers = [
    {
      name: 'John Smith',
      position: 'CEO',
      image: '/images/team/ceo.jpg'
    },
    {
      name: 'Sarah Johnson',
      position: 'Operations Director',
      image: '/images/team/operations.jpg'
    },
    {
      name: 'Michael Brown',
      position: 'Finance Director',
      image: '/images/team/finance.jpg'
    }
  ]
  
  const stats = [
    { value: '10+', label: 'Years of Experience' },
    { value: '5000+', label: 'Happy Clients' },
    { value: '$50M+', label: 'Loans Disbursed' },
    { value: '98%', label: 'Client Satisfaction' }
  ]
  </script>
  
  <style scoped>
  .animate-fade-in-up {
    animation: fadeInUp 0.6s ease-out forwards;
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