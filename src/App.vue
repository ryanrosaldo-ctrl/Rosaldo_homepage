<template>
  <div class="bg-blue-100 text-gray-800 min-h-screen">
    <header class="bg-yellow-400 py-12 text-center">
      <h1 class="text-3xl md:text-5xl font-bold mb-4">My Student Portfolio 😎</h1>
      <p class="text-lg mb-6">Hey, I'm Ryan Kristoffer M. Rosaldo, a student at University of Santo Tomas. Check out my stuff!</p>
      <button @click="scrollToSection('projects')" class="bg-green-500 text-white px-4 py-2 rounded font-semibold hover:bg-green-600">See My Projects</button>
    </header>

    <section id="about" class="py-10 px-4">
      <h2 class="text-2xl font-bold text-center mb-6">About Me</h2>
      <div class="flex flex-col md:flex-row items-center max-w-4xl mx-auto">
        <p class="text-base leading-relaxed">Hi! I'm an Information Systems major in college. I love coding and hanging out with friends. This is my first big project, so it's kinda basic but cool!</p>
      </div>
    </section>

    <section class="bg-pink-200 py-10 px-4">
      <h2 class="text-2xl font-bold text-center mb-6">My Education</h2>
      <div class="max-w-2xl mx-auto text-center">
        <p class="text-lg mb-4">I'm studying at University of Santo Tomas and I'm taking classes in Information Systems and stuff.</p>
        <ul class="list-disc list-inside text-left">
          <li>Favorite Class: EleBA </li>
          <li>Graduation: 2025 (hopefully!)</li>
        </ul>
      </div>
    </section>

    <section id="projects" class="py-10 px-4">
      <h2 class="text-2xl font-bold text-center mb-6">My School Projects</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl mx-auto">
        <div class="bg-white p-4 rounded shadow">
          <h3 class="font-semibold mb-2">Simple Calculator App</h3>
          <p class="text-sm mb-4">Made a basic calc in JS. It's not perfect but it works!</p>
          <a href="#" class="text-blue-500 underline">View on GitHub</a>
        </div>
        <div class="bg-white p-4 rounded shadow">
          <h3 class="font-semibold mb-2">To-Do List</h3>
          <p class="text-sm mb-4">A list app for my homework. Added some colors to make it fun.</p>
          <a href="#" class="text-blue-500 underline">View on GitHub</a>
        </div>
      </div>
    </section>

    <section class="bg-green-200 py-10 px-4">
      <h2 class="text-2xl font-bold text-center mb-6">Fun Facts About Me</h2>
      <div class="max-w-2xl mx-auto text-center">
        <p class="text-lg mb-4">I like pizza 🍕 and playing video games. Also, I have a pet cat named Chekko!</p>
        <ul class="list-disc list-inside text-left">
          <li>Hobby: working out</li>
          <li>Dream Job: Game Developer</li>
        </ul>
      </div>
    </section>

    <section id="contact" class="py-10 px-4">
      <h2 class="text-2xl font-bold text-center mb-6">Contact Me</h2>
      <form @submit.prevent="handleSubmit" class="max-w-md mx-auto">
        <input v-model="form.name" type="text" placeholder="Your Name" class="w-full p-2 mb-3 border rounded" required>
        <input v-model="form.email" type="email" placeholder="Your Email" class="w-full p-2 mb-3 border rounded" required>
        <textarea v-model="form.message" placeholder="Say Hi!" class="w-full p-2 mb-3 border rounded" rows="3" required></textarea>
        <button type="submit" class="w-full bg-blue-500 text-white py-2 rounded hover:bg-blue-600">Send</button>
      </form>
    </section>

    <footer class="bg-gray-300 py-6 text-center">
      <p>&copy; 2023 Ryan Kristoffer M. Rosaldo. Made for class! Follow me on <a href="#" class="text-blue-500 underline">Instagram</a>.</p>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'App',
  setup() {
    const form = ref({
      name: '',
      email: '',
      message: ''
    });

    const handleSubmit = () => {
      alert('Thanks for the message! (Demo only - no real sending)');
      form.value = { name: '', email: '', message: '' };
    };

    const scrollToSection = (id) => {
      document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
    };

    return {
      form,
      handleSubmit,
      scrollToSection
    };
  }
};
</script>

<style>
</style>