<script setup>
import { onMounted,ref } from 'vue'
import VanillaTilt from 'vanilla-tilt'
const showResume = ref(false)
onMounted(() => {
  // 3D Tilt for all project cards
  const tiltCards = document.querySelectorAll('.tilt-card')
  VanillaTilt.init(tiltCards, { max: 25, speed: 400, glare: true, 'max-glare': 0.5 })

  // Fade-in animation for all sections
  const sections = document.querySelectorAll('section')
  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) entry.target.classList.add('visible')
    })
  }, { threshold: 0.1 })
  sections.forEach(section => observer.observe(section))
})
</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-white via-indigo-50 to-white text-gray-800 font-sans">


    <!-- Navbar -->
    <nav class="flex justify-between items-center py-6 px-8 bg-white/70 backdrop-blur shadow-md fixed w-full z-20">
      <div class="text-2xl font-bold tracking-tight text-indigo-600">Arin Vashisth</div>
      <div class="flex gap-6 text-lg font-medium">
        <a href="#about" class="hover:text-indigo-500 hover:underline underline-offset-4 transition">About</a>
        <a href="#skills" class="hover:text-indigo-500 hover:underline underline-offset-4 transition">Skills</a>
        <a href="#projects" class="hover:text-indigo-500 hover:underline underline-offset-4 transition">Projects</a>
        <a href="#education" class="hover:text-indigo-500 hover:underline underline-offset-4 transition">Education</a>
        <a href="#contact" class="hover:text-indigo-500 hover:underline underline-offset-4 transition">Contact</a>
        <a href="#resume" class="px-3 py-1 bg-indigo-600 text-white rounded hover:bg-indigo-700 transition">Resume</a>
      </div>
    </nav>

    <!-- Hero -->
    <section id="hero" class="scroll-mt-24 pt-32 pb-12 flex flex-col items-center text-center bg-gradient-to-b from-indigo-100 to-transparent shadow-lg rounded-lg mx-6 md:mx-auto max-w-4xl fade-section">
      <img loading="lazy" src="https://ui-avatars.com/api/?name=Arin+Vashisth&background=4F46E5&color=fff&size=128" alt="Arin Vashisth" class="rounded-full shadow-lg mb-4 w-32 h-32 object-cover border-4 border-indigo-200" />
      <h1 class="text-4xl md:text-5xl font-extrabold mb-2 bg-gradient-to-r from-indigo-500 via-blue-600 to-purple-500 bg-clip-text text-transparent">Arin Vashisth</h1>
      <p class="text-lg md:text-xl mb-2 font-medium text-indigo-700">Aspiring Software Developer & Data Science Student</p>
      <p class="mt-1 text-sm text-gray-600 italic">🌱 Learning. Building. Evolving.</p>
      <div class="flex gap-4 justify-center mt-3">
        <a href="https://linkedin.com/in/arin-vashisth-059755264/" target="_blank" class="hover:scale-110 transition">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" class="w-7 h-7" />
        </a>
        <a href="https://github.com/arinVashisth" target="_blank" class="hover:scale-110 transition">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" class="w-7 h-7" />
        </a>
        <a href="mailto:22f3001906@ds.study.iitm.ac.in" class="hover:scale-110 transition">
          <svg class="w-7 h-7 text-indigo-600" fill="currentColor" viewBox="0 0 24 24"><path d="M2 4v16h20V4H2zm18 2v.511l-8 6.222-8-6.222V6h16zm0 12H4V8.489l8 6.222 8-6.222V18z"/></svg>
        </a>
      </div>
      <div class="mt-4 text-sm text-gray-600">Email: 22f3001906@ds.study.iitm.ac.in &nbsp;|&nbsp; Phone: 9306224292</div>
    </section>

    <!-- About -->
    <section id="about" class="scroll-mt-24 mt-5 fade-section max-w-3xl mx-auto py-12 px-6 shadow-lg rounded-2xl border border-white/30 bg-white/80 backdrop-blur transition-all duration-500">
      <h2 class="text-3xl font-bold mb-4 text-indigo-600">About Me</h2>
      <p class="text-gray-700 leading-relaxed text-lg">
        I'm Arin Vashisth, a software developer and Data Science undergrad at IIT Madras. My passion for tech began with an early fascination for data-driven decision making — something I discovered through school and tech creators online. 
        <br /><br />
        I’ve since built projects in machine learning and full-stack development, including an AI-powered Resume Analyzer using React, Flask, and NLP. I enjoy solving DSA problems, exploring patterns, and thinking analytically.
        <br /><br />
        I'm aiming to work at a product-based company or contribute to open source. Outside coding, I enjoy badminton and tech events.
      </p>
    </section>

    <!-- Skills -->
    <section id="skills" class="scroll-mt-24 mt-5 fade-section max-w-3xl mx-auto py-12 px-6 shadow-lg rounded-2xl border border-white/30 bg-white/80 backdrop-blur">
      <h2 class="text-3xl font-bold mb-8 text-indigo-600 text-center">Skills</h2>
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 text-gray-700 text-base sm:text-lg">
        
        <div>
          <h3 class="font-semibold text-indigo-500 mb-2">Languages</h3>
          <ul class="list-disc pl-5 space-y-1">
            <li>Python, C++</li>
            <li>JavaScript, HTML5, CSS3</li>
          </ul>
        </div>

        <div>
          <h3 class="font-semibold text-indigo-500 mb-2">Frameworks & Libraries</h3>
          <ul class="list-disc pl-5 space-y-1">
            <li>Vue.js, React.js</li>
            <li>Flask, scikit-learn, spaCy</li>
            <li>Tailwind CSS</li>
          </ul>
        </div>

        <div>
          <h3 class="font-semibold text-indigo-500 mb-2">Tools & Platforms</h3>
          <ul class="list-disc pl-5 space-y-1">
            <li>Git, GitHub, Postman</li>
            <li>Vercel, Render, Replit</li>
            <li>VS Code, Jupyter Notebook</li>
          </ul>
        </div>

        <div>
          <h3 class="font-semibold text-indigo-500 mb-2">Core Skills</h3>
          <ul class="list-disc pl-5 space-y-1">
            <li>Problem Solving, DSA</li>
            <li>Object-Oriented Programming (OOP)</li>
            <li>Basic Business Analysis</li>
            <li>REST APIs (basic)</li>
          </ul>
        </div>

        <div>
          <h3 class="font-semibold text-indigo-500 mb-2">Machine Learning & NLP</h3>
          <ul class="list-disc pl-5 space-y-1">
            <li>TF-IDF, Cosine Similarity</li>
            <li>NER with spaCy</li>
            <li>Model pipelines with scikit-learn</li>
          </ul>
        </div>

        <div>
          <h3 class="font-semibold text-indigo-500 mb-2">Other</h3>
          <ul class="list-disc pl-5 space-y-1">
            <li>Responsive Design, UI/UX basics</li>
            <li>PDF data extraction (PyPDF2, etc.)</li>
            <li>Working in fullstack architecture</li>
          </ul>
        </div>

      </div>
    </section>

    <!-- Projects -->
    <section id="projects" class="scroll-mt-24 fade-section max-w-6xl mx-auto py-16 px-6">
      <h2 class="text-4xl font-bold mb-12 text-center text-indigo-600">Projects</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12">

        <!-- Project: AI Resume Analyzer -->
        <div class="tilt-card group relative rounded-3xl p-6 shadow-xl border hover:border-white/40 transition duration-500 hover:-translate-y-2 hover:shadow-indigo-300/40">
          <div class="transition-transform duration-700 ease-in-out group-hover:rotate-[1deg] group-hover:scale-[1.02]">
            <h3 class="text-2xl font-semibold text-gray-800 mb-3">AI Resume Analyzer</h3>
            <span class="inline-block bg-indigo-100 text-indigo-700 text-xs font-semibold px-2 py-1 rounded mb-2">Fullstack · Real-World</span>
            <p class="text-gray-700 leading-relaxed mb-2">
              AI-powered tool that analyzes resumes against job descriptions, highlights matched/missing skills, and provides suggestions using NLP.
            </p>
            <p class="text-sm text-gray-600 mb-2">Tech: React (Vite), Flask, spaCy, scikit-learn, Tailwind CSS</p>
            <a href="https://analyzer-frontend-ebon.vercel.app/" target="_blank" class="text-indigo-600 hover:underline text-sm">🔗 Live Demo</a>
          </div>
        </div>

        <!-- Project: Smart HealthCare Tracker -->
        <div class="tilt-card group relative rounded-3xl p-6 shadow-xl border hover:border-white/40 transition duration-500 hover:-translate-y-2 hover:shadow-indigo-300/40">
          <div class="transition-transform duration-700 ease-in-out group-hover:rotate-[1deg] group-hover:scale-[1.02]">
            <h3 class="text-2xl font-semibold text-gray-800 mb-3">Smart HealthCare Tracker</h3>
            <span class="inline-block bg-indigo-100 text-indigo-700 text-xs font-semibold px-2 py-1 rounded mb-2">Web App · Real-World</span>
            <p class="text-gray-700 leading-relaxed mb-2">
              A responsive website that helps users find doctors, track health metrics, and manage appointments. Focus on clean UI and accessibility.
            </p>
            <p class="text-sm text-gray-600 mb-2">Tech: React (Vite), HTML, CSS, JS, Tailwind, Python, scikit-learn, Pandas</p>
            <a href="https://smart-health-care-frontend.vercel.app/" target="_blank" class="text-indigo-600 hover:underline text-sm">🔗 Live Demo</a>
          </div>
        </div>

        <!-- Project: Soil Moisture Prediction -->
        <div class="tilt-card group relative rounded-3xl p-6 shadow-xl border hover:border-white/40 transition duration-500 hover:-translate-y-2 hover:shadow-indigo-300/40">
          <div class="transition-transform duration-700 ease-in-out group-hover:rotate-[1deg] group-hover:scale-[1.02]">
            <h3 class="text-2xl font-semibold text-gray-800 mb-3">Soil Moisture Prediction</h3>
            <span class="inline-block bg-indigo-100 text-indigo-700 text-xs font-semibold px-2 py-1 rounded mb-2">ML · Time Series</span>
            <p class="text-gray-700 leading-relaxed">
              Built a time series model to predict soil moisture for the next 5–10 years using data collected via QGIS from Sentinel-2 and Landsat satellites.
            </p>
            <p class="text-sm text-gray-600 mt-2">Tech: Python, scikit-learn, Pandas, QGIS</p>
          </div>
        </div>

        <!-- Project: Newspaper Text Fetcher -->
        <div class="tilt-card group relative rounded-3xl p-6 shadow-xl border hover:border-white/40 transition duration-500 hover:-translate-y-2 hover:shadow-indigo-300/40">
          <div class="transition-transform duration-700 ease-in-out group-hover:rotate-[1deg] group-hover:scale-[1.02]">
            <h3 class="text-2xl font-semibold text-gray-800 mb-3">Newspaper Text Fetcher</h3>
            <span class="inline-block bg-yellow-100 text-yellow-800 text-xs font-semibold px-2 py-1 rounded mb-2">Prototype · Accessibility</span>
            <p class="text-gray-700 leading-relaxed">
              Fetches printed newspaper text, translates it into any language, and reads it aloud — aiming to help visually impaired users stay informed.
            </p>
            <p class="text-sm text-gray-600 mt-2 italic">Note: Under development, early-stage prototype.</p>
          </div>
        </div>

      </div>
    </section>

    <!-- Education -->
    <section id="education" class="scroll-mt-24 fade-section max-w-3xl mx-auto py-12 px-6 shadow-lg rounded-lg bg-white/80 backdrop-blur">
      <h2 class="text-3xl font-bold mb-4 text-indigo-600">Education</h2>
      
      <div class="space-y-4 text-gray-700 leading-relaxed">
        <div>
          <strong class="text-lg">University of Engineering & Management (UEM), Jaipur</strong><br />
          <span class="text-sm">B.Tech in Computer Science & Engineering — 2022–2026</span>
        </div>

        <div>
          <strong class="text-lg">Indian Institute of Technology (IIT) Madras</strong><br />
          <span class="text-sm">BS in Data Science & Applications (Online) — 2022–Present</span>
        </div>
      </div>
    </section>


    <!-- Experience -->
    <section id="experience" class="scroll-mt-24 mt-5 fade-section max-w-3xl mx-auto py-12 px-6 shadow-lg rounded-lg bg-white/80 backdrop-blur">
      <h2 class="text-3xl font-bold mb-4 text-indigo-600">Experience</h2>
      <div class="text-gray-700 space-y-4 leading-relaxed">

        <p>
          While I haven't had formal work experience or internships yet, I've actively built and contributed to real-world projects that demonstrate my technical capabilities and passion for learning.
        </p>

        <ul class="list-disc pl-5 space-y-2">
          <li>
            <strong>AI Resume Analyzer:</strong> Developed a full-stack application using React, Flask, spaCy, and scikit-learn to evaluate resumes against job descriptions using NLP.
          </li>
          <li>
            <strong>Smart Health Care Tracker:</strong> Built a responsive web platform to help users manage health records and find services. Hosted on Vercel.
          </li>
          <li>
            <strong>Soil Moisture Prediction (ML):</strong> Conducted time-series forecasting using satellite data from QGIS, Landsat 8/9 & Sentinel-2 to analyze soil trends.
          </li>
          <li>
            <strong>Newspaper Text Fetcher:</strong> Created a tool that converts printed newspaper text into readable formats, aiming to assist visually impaired users.
          </li>
        </ul>

        <p>
          These experiences have helped me strengthen my skills in full-stack development, machine learning, and practical problem-solving, preparing me for future professional roles.
        </p>
      </div>
    </section>


    <!-- Co-Curricular Activities -->
    <section id="activities" class="scroll-mt-24 mt-5 fade-section max-w-3xl mx-auto py-12 px-6 shadow-lg rounded-lg bg-white/80 backdrop-blur">
      <h2 class="text-3xl font-bold mb-4 text-indigo-600">Co-Curricular Activities</h2>
      <ul class="list-disc pl-5 space-y-2 text-gray-700">

        <li>
          <strong>Member – Web Development Club, IIT Madras</strong><br />
          Collaborating with peers on web projects and learning modern frameworks like Vue.js and Tailwind CSS through club-led sessions and builds.
        </li>

        <li>
          <strong>Hackathon Participant – Internal Events</strong><br />
          Took part in campus-based hackathons focused on solving real-world problems using machine learning, web development, and automation tools.
        </li>

        <li>
          <strong>Volunteer – Tech Workshops for Beginners</strong><br />
          Helped conduct beginner-friendly coding sessions and assisted new learners in understanding web basics and Python fundamentals.
        </li>

      </ul>
    </section>

    <!-- Resume Section -->
    <section id="resume" class="scroll-mt-24 mt-5 fade-section max-w-3xl mx-auto py-12 px-6 flex flex-col items-center shadow-lg rounded-lg bg-white/80 backdrop-blur">
      <h2 class="text-3xl font-bold mb-4 text-indigo-600">Resume</h2>

      <!-- Trigger Button -->
      <button @click="showResume = true" class="cursor-pointer inline-block px-6 py-3 bg-indigo-600 text-white rounded-lg shadow hover:bg-indigo-700 transition font-semibold">
        View Resume
      </button>
    </section>




    <!-- Contact -->
    <section id="contact" class="scroll-mt-24 mt-5 fade-section max-w-3xl mx-auto py-12 px-6 flex flex-col items-center shadow-lg rounded-lg bg-white/80 backdrop-blur">
      <h2 class="text-3xl font-bold mb-4 text-indigo-600">Contact Me</h2>
      <p class="text-gray-700 text-center mb-4">
        I'm always open to exciting opportunities, collaborations, or just a friendly chat. Feel free to reach out!
      </p>

      <div class="flex space-x-4 mt-2">
        <!-- Email -->
        <a href="mailto:22f3001906@ds.study.iitm.ac.in" class="text-indigo-600 hover:text-indigo-800 font-medium underline">
          Email
        </a>

        <!-- LinkedIn -->
        <a href="https://www.linkedin.com/in/arin-vashisth-059755264/" target="_blank" rel="noopener" class="text-indigo-600 hover:text-indigo-800 font-medium underline">
          LinkedIn
        </a>
      </div>
    </section>
      

    <!-- Footer -->
    <footer class="text-center py-6 text-gray-400 text-sm bg-gray-100 mt-12 rounded-t-lg shadow-inner">
      &copy; 2025 Arin Vashisth. Built with Vue & Tailwind CSS.
    </footer>

    <!-- Fixed Modal (Overlay Style) -->
    <transition name="fade">
      <div v-if="showResume" class="fixed inset-0 z-50 flex items-center justify-center bg-black/40">
        <div class="bg-white w-full max-w-3xl mx-4 p-6 rounded-xl shadow-2xl relative">
          
          <!-- Close Button -->
          <button @click="showResume = false" class="absolute top-3 right-3 text-gray-500 hover:text-red-600 text-2xl font-bold cursor-pointer">
            &times;
          </button>

          <h3 class="text-xl font-semibold mb-4 text-indigo-700">My Resume</h3>

          <!-- Embedded PDF -->
          <iframe
            src="/Arin.pdf"
            class="w-full h-[500px] rounded-lg border"
            frameborder="0"
          ></iframe>

          <!-- Download Button -->
          <div class="mt-4 flex justify-end">
            <a
              href="/Arin.pdf"
              download
              class="px-5 py-2 bg-indigo-600 text-white rounded hover:bg-indigo-700 font-medium"
            >
              Download Resume
            </a>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<style>
.fade-section {
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s ease-in-out;
}
.fade-section.visible {
  opacity: 2;
  transform: translateY(0);
}

.tilt-card {
  background: rgba(255, 255, 255, 0.45); /* Light glassmorphism */
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

</style>
