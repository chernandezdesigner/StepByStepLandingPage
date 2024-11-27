<template>
  <div class="font-sans text-gray-900 bg-gray-50">
    <!-- Fixed Header -->
    <header class="fixed top-0 left-0 right-0 bg-white shadow-sm z-50">
      <div class="container mx-auto px-4 py-4 flex justify-between items-center">
        <div class="text-2xl font-bold text-gray-900">StepByStep Mortgage</div>
        <nav class="hidden md:flex space-x-6">
          <a href="#features" class="text-gray-600 hover:text-sky-400 transition duration-300">Key Benefits</a>
          <a href="#how-it-works" class="text-gray-600 hover:text-sky-400 transition duration-300">Our Process</a>
          <a href="#preview" class="text-gray-600 hover:text-sky-400 transition duration-300">App Preview</a>
        </nav>
        <button class="bg-sky-400 text-white px-4 py-2 rounded-md hover:bg-sky-500 transition duration-300">
          Get Started
        </button>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="pt-32 pb-24 px-4 bg-gradient-to-br from-sky-50 to-white overflow-hidden">
      <div class="container mx-auto text-center relative">
        <div class="absolute top-0 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-sky-100 rounded-full filter blur-3xl opacity-70"></div>
        <div class="absolute bottom-0 right-0 w-64 h-64 bg-sky-200 rounded-full filter blur-2xl opacity-60"></div>
        <div class="relative z-10">
          <h1 class="text-5xl font-bold mb-6 leading-tight">Create Your Ideal Mortgage</h1>
          <h2 class="text-4xl font-bold text-sky-500 mb-8">Have Total Agency Throughout Your Process</h2>
          <p class="text-xl font-medium text-gray-700 mb-12 max-w-2xl mx-auto">
            No more dealing with pushy salespeople, take your mortgage to the finish line all on your own.
          </p>
          <form @submit.prevent="submitWaitlist" class="max-w-md mx-auto space-y-4">
            <input
              v-model="email"
              type="email"
              placeholder="Enter your email"
              class="w-full px-4 py-3 rounded-md border-2 border-gray-300 focus:outline-none focus:border-sky-400"
              required
            />
            <button
              type="submit"
              :disabled="isSubmitting"
              class="w-full bg-sky-400 text-white px-6 py-3 rounded-md hover:bg-sky-500 transition duration-300 disabled:opacity-50"
            >
              {{ isSubmitting ? 'Joining...' : 'Join Our Waitlist' }}
            </button>
            <p v-if="errorMessage" class="text-red-500 text-sm mt-2">{{ errorMessage }}</p>
          </form>
        </div>
      </div>
      <div class="mt-16 relative">
        <div class="absolute inset-0 bg-sky-100 transform -skew-y-6"></div>
        <div class="relative container mx-auto">
          <div class="grid md:grid-cols-3 gap-8 px-4">
            <div class="bg-white p-6 rounded-lg shadow-lg">
              <CheckCircleIcon class="w-12 h-12 text-sky-400 mb-4" />
              <h3 class="text-xl font-bold mb-2">Tailored Solutions</h3>
              <p class="text-gray-600">Customized mortgage options for your unique situation</p>
            </div>
            <div class="bg-white p-6 rounded-lg shadow-lg">
              <ShieldIcon class="w-12 h-12 text-sky-400 mb-4" />
              <h3 class="text-xl font-bold mb-2">Data Protection</h3>
              <p class="text-gray-600">Your information is secure and never sold</p>
            </div>
            <div class="bg-white p-6 rounded-lg shadow-lg">
              <TrendingUpIcon class="w-12 h-12 text-sky-400 mb-4" />
              <h3 class="text-xl font-bold mb-2">Guided Experience</h3>
              <p class="text-gray-600">Expert support at every stage of your journey</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section id="features" class="py-24 px-4 bg-white">
      <div class="container mx-auto">
        <h2 class="text-4xl font-bold mb-12 text-center">Key Benefits</h2>
        <div class="grid md:grid-cols-2 gap-12">
          <div class="bg-gray-50 p-8 rounded-lg shadow-md">
            <ShieldIcon class="w-16 h-16 text-sky-400 mb-6" />
            <h3 class="text-2xl font-bold mb-4">Trust & Privacy First</h3>
            <p class="text-gray-700">
              Experience a mortgage platform where all inquiries are managed in-house. Our revenue comes from subscribed lenders, ensuring your data remains protected and your interests come first.
            </p>
          </div>
          <div class="bg-gray-50 p-8 rounded-lg shadow-md">
            <NetworkIcon class="w-16 h-16 text-sky-400 mb-6" />
            <h3 class="text-2xl font-bold mb-4">AI-Powered Matching</h3>
            <p class="text-gray-700">
              Our advanced AI technology connects you with local lenders who understand your specific needs and area. Get personalized mortgage options that truly fit your circumstances.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- How it Works Section -->
    <section id="how-it-works" class="py-24 px-4 bg-gray-50 overflow-hidden">
      <div class="container mx-auto relative">
        <h2 class="text-4xl font-bold mb-4 text-center">Our Process</h2>
        <h3 class="text-xl text-gray-600 mb-16 text-center">Your Journey to the Perfect Mortgage</h3>
        
        <!-- Decorative elements -->
        <div class="absolute top-1/2 left-0 w-full h-1 bg-sky-200 transform -translate-y-1/2"></div>
        <div class="absolute top-1/2 left-1/4 w-4 h-4 bg-sky-400 rounded-full transform -translate-x-1/2 -translate-y-1/2"></div>
        <div class="absolute top-1/2 left-1/2 w-4 h-4 bg-sky-400 rounded-full transform -translate-x-1/2 -translate-y-1/2"></div>
        <div class="absolute top-1/2 left-3/4 w-4 h-4 bg-sky-400 rounded-full transform -translate-x-1/2 -translate-y-1/2"></div>
        
        <div class="grid md:grid-cols-3 gap-8 relative z-10">
          <div class="bg-white p-8 rounded-lg shadow-md flex flex-col h-full">
            <div class="w-16 h-16 bg-sky-400 text-white rounded-full flex items-center justify-center text-2xl font-bold mb-6">1</div>
            <h4 class="text-xl font-bold mb-4">Define Your Goals</h4>
            <p class="text-gray-700 flex-grow">
              Use our intuitive application to outline your mortgage objectives quickly and efficiently.
            </p>
            <FileTextIcon class="w-16 h-16 text-sky-400 mt-6 self-center" />
          </div>
          <div class="bg-white p-8 rounded-lg shadow-md flex flex-col h-full">
            <div class="w-16 h-16 bg-sky-400 text-white rounded-full flex items-center justify-center text-2xl font-bold mb-6">2</div>
            <h4 class="text-xl font-bold mb-4">Explore Tailored Options</h4>
            <p class="text-gray-700 flex-grow">
              Review curated offers from local lenders, complete with their expertise and track record, all in your personal dashboard.
            </p>
            <ListIcon class="w-16 h-16 text-sky-400 mt-6 self-center" />
          </div>
          <div class="bg-white p-8 rounded-lg shadow-md flex flex-col h-full">
            <div class="w-16 h-16 bg-sky-400 text-white rounded-full flex items-center justify-center text-2xl font-bold mb-6">3</div>
            <h4 class="text-xl font-bold mb-4">Navigate with Confidence</h4>
            <p class="text-gray-700 flex-grow">
              We guide you through every document and disclosure until closing, ensuring you're fully informed and comfortable with your decisions.
            </p>
            <CheckCircleIcon class="w-16 h-16 text-sky-400 mt-6 self-center" />
          </div>
        </div>
      </div>
    </section>
    <!-- Screenshot Section -->
    <section id="preview" class="py-24 px-4 bg-white">
      <div class="container mx-auto">
        <h2 class="text-4xl font-bold mb-12 text-center">App Preview</h2>
        <div class="grid md:grid-cols-2 gap-8">
          <div class="bg-gray-100 rounded-lg shadow-inner p-8">
            <div class="bg-gray-300 h-96 rounded-lg flex items-center justify-center">
              <ImageIcon class="w-24 h-24 text-gray-600" />
            </div>
          </div>
          <div class="bg-gray-100 rounded-lg shadow-inner p-8">
            <div class="bg-gray-300 h-96 rounded-lg flex items-center justify-center">
              <ImageIcon class="w-24 h-24 text-gray-600" />
            </div>
          </div>
        </div>
        <p class="mt-6 text-gray-600 text-center">Experience the future of mortgage applications - coming soon!</p>
      </div>
    </section>

    <!-- Final CTA Section -->
    <section class="py-24 px-4 bg-gradient-to-br from-sky-400 to-sky-600 text-white overflow-hidden relative">
      <div class="container mx-auto relative z-10">
        <div class="max-w-4xl mx-auto text-center">
          <h2 class="text-4xl md:text-5xl font-bold mb-8 leading-tight">
            Ready to Revolutionize Your Mortgage Experience?
          </h2>
          <p class="text-xl mb-12 text-sky-100">
            Join thousands of homeowners who are taking control of their mortgage journey. Be the first to know when we launch!
          </p>
          <form @submit.prevent="submitWaitlist" class="max-w-md mx-auto space-y-4">
            <input
              v-model="email"
              type="email"
              placeholder="Enter your email"
              class="w-full px-4 py-3 rounded-md border-2 border-sky-300 bg-white/10 placeholder-sky-200 text-white focus:outline-none focus:border-white focus:ring-2 focus:ring-white"
              required
            />
            <button
              type="submit"
              :disabled="isSubmitting"
              class="w-full bg-white text-sky-600 px-6 py-3 rounded-md hover:bg-sky-100 transition duration-300 font-semibold disabled:opacity-50"
            >
              {{ isSubmitting ? 'Joining...' : 'Join the Waitlist' }}
            </button>
            <p v-if="errorMessage" class="text-red-500 text-sm mt-2">{{ errorMessage }}</p>
          </form>
          <p class="mt-4 text-sm text-sky-200">
            By joining, you agree to our <a href="#" class="underline hover:text-white">Terms of Service</a> and <a href="#" class="underline hover:text-white">Privacy Policy</a>.
          </p>
        </div>
      </div>
      <!-- Decorative elements -->
      <div class="absolute top-0 left-0 w-64 h-64 bg-sky-300 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-blob"></div>
      <div class="absolute top-0 right-0 w-64 h-64 bg-sky-400 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-blob animation-delay-2000"></div>
      <div class="absolute -bottom-8 left-20 w-64 h-64 bg-sky-500 rounded-full mix-blend-multiply filter blur-xl opacity-70 animate-blob animation-delay-4000"></div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12 px-4">
      <div class="container mx-auto">
        <div class="grid md:grid-cols-3 gap-8">
          <div>
            <h3 class="text-2xl font-bold mb-4">StepByStep Mortgage</h3>
            <p class="text-gray-400">Revolutionizing the path to homeownership.</p>
          </div>
          <div>
            <h4 class="text-lg font-semibold mb-4">Quick Links</h4>
            <ul class="space-y-2">
              <li><a href="#features" class="text-gray-400 hover:text-white transition duration-300">Key Benefits</a></li>
              <li><a href="#how-it-works" class="text-gray-400 hover:text-white transition duration-300">Our Process</a></li>
              <li><a href="#preview" class="text-gray-400 hover:text-white transition duration-300">App Preview</a></li>
            </ul>
          </div>
          <div>
            <h4 class="text-lg font-semibold mb-4">Legal</h4>
            <ul class="space-y-2">
              <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">Privacy Policy</a></li>
              <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">Terms of Service</a></li>
              <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">Contact Us</a></li>
            </ul>
          </div>
        </div>
        <div class="mt-8 pt-8 border-t border-gray-800 text-center">
          <p>&copy; 2023 StepByStep Mortgage. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { LockIcon, UsersIcon, ImageIcon, CheckCircleIcon, ShieldIcon, TrendingUpIcon, FileTextIcon, ListIcon, CheckSquareIcon, SparkleIcon, NetworkIcon, CompassIcon, ClipboardCheckIcon } from 'lucide-vue-next'

const email = ref('')
const isSubmitting = ref(false)
const errorMessage = ref('')

const submitWaitlist = async () => {
  try {
    isSubmitting.value = true
    errorMessage.value = ''
    
    // Replace this URL with your Google Apps Script deployment URL
    const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbxaYA3ZSiEU_22LIsvy7hwTNQaSM7b2kXctDE5oWPd3w31idJUTAcaMSpmmSsg7EWvazQ/exec'
    
    // Create URL-encoded form data instead of JSON
    const formData = new FormData();
    formData.append('email', email.value);
    
    const response = await fetch(GOOGLE_SCRIPT_URL, {
      method: 'POST',
      mode: 'no-cors',
      body: formData
    });

    // Since we're using no-cors, we won't get a response we can read
    // So we'll just assume success if no error was thrown
    alert('Thank you for joining our waitlist!')
    email.value = ''
  } catch (error) {
    console.error('Error:', error)
    errorMessage.value = 'Failed to join waitlist. Please try again.'
  } finally {
    isSubmitting.value = false
  }
}
</script>

<style scoped>
@keyframes blob {
  0% {
    transform: translate(0px, 0px) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
  100% {
    transform: translate(0px, 0px) scale(1);
  }
}

.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-2000 {
  animation-delay: 2s;
}

.animation-delay-4000 {
  animation-delay: 4s;
}
</style>