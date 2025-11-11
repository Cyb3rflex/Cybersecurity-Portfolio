# Cybersecurity-Portfolio

// Project: cybersecurity-portfolio
// Generated files: package.json, vite.config.js, tailwind.config.js, postcss.config.js,
// src/* (components, pages, data, layouts, hooks, utils), public assets placeholders

// -----------------------------
// File: package.json
// -----------------------------
{
  "name": "cybersecurity-portfolio",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "framer-motion": "^10.12.14",
    "lucide-react": "^0.259.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "autoprefixer": "^10.4.14",
    "postcss": "^8.4.24",
    "tailwindcss": "^3.5.3",
    "vite": "^5.0.0"
  }
}


// -----------------------------
// File: vite.config.js
// -----------------------------
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: {
    port: 5173
  }
})


// -----------------------------
// File: tailwind.config.js
// -----------------------------
export default {
  content: [
    './index.html',
    './src/**/*.{js,jsx,ts,tsx}'
  ],
  theme: {
    extend: {
      colors: {
        cyber: '#0f172a',
        neon: '#00ffd5',
        accent: '#7c3aed'
      },
      boxShadow: {
        'neon-sm': '0 0 8px rgba(0,255,213,0.08), inset 0 0 12px rgba(124,58,237,0.04)'
      }
    }
  },
  plugins: []
}


// -----------------------------
// File: postcss.config.js
// -----------------------------
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}
  }
}


// -----------------------------
// File: public/favicon.ico
// -----------------------------
// (Placeholder - put your favicon here)

// -----------------------------
// File: public/images/avatar.png
// -----------------------------
// (Placeholder - put your avatar here)

// -----------------------------
// File: src/main.jsx
// -----------------------------
import React from 'react'
import { createRoot } from 'react-dom/client'
import App from './App'
import './index.css'

createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
)


// -----------------------------
// File: src/index.css
// -----------------------------
@tailwind base;
@tailwind components;
@tailwind utilities;

html, body, #root {
  height: 100%;
}

body {
  @apply bg-cyber text-slate-100 antialiased;
  font-family: Inter, ui-sans-serif, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
}

// small helper classes
.btn-cyber {
  @apply px-4 py-2 rounded-md bg-gradient-to-r from-accent to-neon text-cyber font-semibold shadow-neon-sm;
}


// -----------------------------
// File: src/tailwind.css
// -----------------------------
/* extra utilities if needed - keep minimal */


// -----------------------------
// File: src/utils/constants.js
// -----------------------------
export const SITE = {
  title: 'Cybersecurity Portfolio',
  owner: 'Your Name',
  description: 'Interactive cybersecurity portfolio and demo projects for students.'
}


// -----------------------------
// File: src/data/projects.js
// -----------------------------
export const projects = [
  {
    id: 'p1',
    title: 'Web App Vulnerability Scanner (Demo)',
    short: 'Small Node-based scanner that highlights common misconfigurations.',
    tech: ['Node', 'Express', 'Axios'],
    image: '/images/project1.png',
    details: 'A teaching tool that demonstrates OWASP Top 10 vulnerabilities safely in a lab environment.'
  },
  {
    id: 'p2',
    title: 'Network Recon CLI (Termux)',
    short: 'CLI tool for passive network enumeration designed for students.',
    tech: ['Python', 'Termux', 'nmap'],
    image: '/images/project2.png',
    details: 'Collects DNS, whois, and basic port info while explaining each step.'
  },
  {
    id: 'p3',
    title: 'Secure Note App (Frontend)',
    short: 'A React demo showing secure local storage patterns and threat modeling.',
    tech: ['React', 'Tailwind'],
    image: '/images/project3.png',
    details: 'Focuses on UX and secure handling of sensitive fields.'
  }
]


// -----------------------------
// File: src/data/skills.js
// -----------------------------
export const skills = [
  { name: 'Web Security', level: 'Advanced' },
  { name: 'Network Recon', level: 'Intermediate' },
  { name: 'Linux / Termux', level: 'Advanced' },
  { name: 'Scripting (Python/Bash)', level: 'Intermediate' }
]


// -----------------------------
// File: src/hooks/useScrollToTop.js
// -----------------------------
import { useEffect } from 'react'
import { useLocation } from 'react-router-dom'

export default function useScrollToTop() {
  const { pathname } = useLocation()
  useEffect(() => {
    window.scrollTo(0, 0)
  }, [pathname])
}


// -----------------------------
// File: src/layouts/MainLayout.jsx
// -----------------------------
import React from 'react'
import Navbar from '../components/Navbar'
import Footer from '../components/Footer'

export default function MainLayout({ children }) {
  return (
    <div className="min-h-screen flex flex-col">
      <Navbar />
      <main className="flex-1 container mx-auto px-4 py-8">{children}</main>
      <Footer />
    </div>
  )
}


// -----------------------------
// File: src/components/Navbar.jsx
// -----------------------------
import React from 'react'
import { Menu, Github } from 'lucide-react'
import { motion } from 'framer-motion'

export default function Navbar() {
  return (
    <nav className="bg-gradient-to-r from-black/20 to-black/10 backdrop-blur-sm border-b border-slate-800">
      <div className="container mx-auto px-4 py-4 flex items-center justify-between">
        <motion.div initial={{ x: -20, opacity: 0 }} animate={{ x: 0, opacity: 1 }} className="flex items-center gap-3">
          <div className="w-10 h-10 rounded-md bg-gradient-to-br from-indigo-700 to-cyan-400 flex items-center justify-center shadow-sm">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="1.5" className="text-white">
              <path d="M3 12h18M12 3v18" />
            </svg>
          </div>
          <div>
            <div className="text-sm font-semibold">Cyberflex Academy</div>
            <div className="text-xs text-slate-400">Cybersecurity Portfolio</div>
          </div>
        </motion.div>

        <div className="flex items-center gap-3">
          <button className="hidden md:inline-flex btn-cyber">Get the Lab</button>
          <a className="p-2 rounded-md hover:bg-white/5" href="#projects" aria-label="projects">
            <Github size={18} />
          </a>
          <button className="md:hidden p-2 rounded-md hover:bg-white/5"><Menu size={18} /></button>
        </div>
      </div>
    </nav>
  )
}


// -----------------------------
// File: src/components/Footer.jsx
// -----------------------------
import React from 'react'

export default function Footer() {
  return (
    <footer className="border-t border-slate-800 bg-transparent">
      <div className="container mx-auto px-4 py-6 text-sm text-slate-400 flex justify-between">
        <div>© {new Date().getFullYear()} Cyberflex Academy</div>
        <div>Built with ❤️ • React + Tailwind + Framer</div>
      </div>
    </footer>
  )
}


// -----------------------------
// File: src/components/SectionHeader.jsx
// -----------------------------
import React from 'react'
import { motion } from 'framer-motion'

export default function SectionHeader({ title, subtitle }) {
  return (
    <div className="mb-6">
      <motion.h2 className="text-2xl font-bold" initial={{ y: 10, opacity: 0 }} animate={{ y: 0, opacity: 1 }}>{title}</motion.h2>
      {subtitle && <div className="text-sm text-slate-400 mt-1">{subtitle}</div>}
    </div>
  )
}


// -----------------------------
// File: src/components/ProjectCard.jsx
// -----------------------------
import React from 'react'
import { Motion, motion } from 'framer-motion'

export default function ProjectCard({ project, onOpen }) {
  return (
    <motion.div whileHover={{ y: -6 }} className="bg-slate-900/40 p-4 rounded-lg shadow-md border border-slate-800">
      <img src={project.image} alt={project.title} className="w-full h-40 object-cover rounded-md mb-3" />
      <div className="flex justify-between items-start">
        <div>
          <h3 className="font-semibold">{project.title}</h3>
          <p className="text-sm text-slate-400">{project.short}</p>
        </div>
        <div className="text-xs text-slate-300">{project.tech.join(' • ')}</div>
      </div>
      <div className="mt-4 flex justify-end">
        <button onClick={() => onOpen(project)} className="btn-cyber">View</button>
      </div>
    </motion.div>
  )
}


// -----------------------------
// File: src/components/ProjectModal.jsx
// -----------------------------
import React from 'react'
import { X } from 'lucide-react'
import { motion } from 'framer-motion'

export default function ProjectModal({ project, onClose }) {
  if (!project) return null
  return (
    <div className="fixed inset-0 z-50 flex items-center justify-center">
      <div className="absolute inset-0 bg-black/70" onClick={onClose}></div>
      <motion.div initial={{ scale: 0.9, opacity: 0 }} animate={{ scale: 1, opacity: 1 }} className="relative max-w-3xl w-full bg-slate-900 p-6 rounded-lg border border-slate-800">
        <button className="absolute top-3 right-3 p-2 rounded-md hover:bg-white/5" onClick={onClose}><X size={18} /></button>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
          <img src={project.image} alt="project" className="w-full h-48 object-cover rounded-md md:col-span-1" />
          <div className="md:col-span-2">
            <h3 className="text-xl font-bold">{project.title}</h3>
            <p className="text-slate-400 mt-2">{project.details}</p>
            <div className="mt-4 text-sm text-slate-300">Tech: {project.tech.join(', ')}</div>
            <div className="mt-6">
              <a href="#" className="btn-cyber">Open Sandbox</a>
            </div>
          </div>
        </div>
      </motion.div>
    </div>
  )
}


// -----------------------------
// File: src/pages/Home.jsx
// -----------------------------
import React, { useState } from 'react'
import SectionHeader from '../components/SectionHeader'
import { projects } from '../data/projects'
import ProjectCard from '../components/ProjectCard'
import ProjectModal from '../components/ProjectModal'
import { motion } from 'framer-motion'

export default function Home() {
  const [open, setOpen] = useState(null)
  return (
    <div>
      <section className="py-8">
        <div className="grid md:grid-cols-2 gap-8 items-center">
          <div>
            <h1 className="text-4xl font-extrabold">Interactive Cybersecurity Portfolio</h1>
            <p className="mt-4 text-slate-400">Designed for students — live labs, case studies, guided demos, and clear notes that teach why vulnerabilities exist and how to fix them.</p>
            <div className="mt-6 flex gap-3">
              <a className="btn-cyber" href="#projects">Explore Projects</a>
              <a className="px-4 py-2 rounded-md border border-slate-700 text-sm" href="#about">About the course</a>
            </div>
          </div>
          <motion.div initial={{ scale: 0.98 }} animate={{ scale: 1 }} className="bg-gradient-to-br from-slate-800/60 to-slate-900 p-6 rounded-lg">
            <div className="grid grid-cols-2 gap-4">
              <div className="p-4 border border-slate-800 rounded">Labs Completed<br /><strong className="text-xl">12</strong></div>
              <div className="p-4 border border-slate-800 rounded">Projects<br /><strong className="text-xl">3</strong></div>
              <div className="p-4 border border-slate-800 rounded">Students<br /><strong className="text-xl">150+</strong></div>
              <div className="p-4 border border-slate-800 rounded">Challenges<br /><strong className="text-xl">20</strong></div>
            </div>
          </motion.div>
        </div>
      </section>

      <section id="projects" className="py-8">
        <SectionHeader title="Projects" subtitle="Hands-on demos and teaching projects" />
        <div className="grid md:grid-cols-3 gap-6">
          {projects.map(p => <ProjectCard key={p.id} project={p} onOpen={setOpen} />)}
        </div>
      </section>

      <section id="about" className="py-8">
        <SectionHeader title="About the Course" subtitle="What students will learn" />
        <div className="grid md:grid-cols-2 gap-6">
          <div>
            <h4 className="font-semibold">Approach</h4>
            <p className="text-slate-400 mt-2">Practical labs, threat modeling, and responsible disclosure practices. Every project includes a learning guide explaining the risk, impact, and mitigation.</p>
          </div>
          <div>
            <h4 className="font-semibold">Outcomes</h4>
            <ul className="list-disc list-inside text-slate-400 mt-2">
              <li>Understand OWASP Top 10</li>
              <li>Run safe reconnaissance in a lab</li>
              <li>Write simple exploit proofs of concept for learning</li>
            </ul>
          </div>
        </div>
      </section>

      <ProjectModal project={open} onClose={() => setOpen(null)} />
    </div>
  )
}


// -----------------------------
// File: src/pages/Projects.jsx
// -----------------------------
import React from 'react'
import SectionHeader from '../components/SectionHeader'
import { projects } from '../data/projects'
import ProjectCard from '../components/ProjectCard'

export default function Projects() {
  return (
    <div>
      <SectionHeader title="All Projects" subtitle="Explore each teaching project" />
      <div className="grid md:grid-cols-3 gap-6">
        {projects.map(p => <ProjectCard key={p.id} project={p} onOpen={() => {}} />)}
      </div>
    </div>
  )
}


// -----------------------------
// File: src/pages/ProjectDetails.jsx
// -----------------------------
import React from 'react'
import { useParams } from 'react-router-dom'
import { projects } from '../data/projects'

export default function ProjectDetails() {
  const { id } = useParams()
  const project = projects.find(p => p.id === id)
  if (!project) return <div>Not found</div>
  return (
    <div>
      <h1 className="text-2xl font-bold">{project.title}</h1>
      <p className="text-slate-400 mt-2">{project.details}</p>
    </div>
  )
}


// -----------------------------
// File: src/pages/About.jsx
// -----------------------------
import React from 'react'
import SectionHeader from '../components/SectionHeader'
import { skills } from '../data/skills'

export default function About() {
  return (
    <div>
      <SectionHeader title="About the Instructor" subtitle="Short bio" />
      <p className="text-slate-400">Instructor: Cyberflex — full stack dev and cybersecurity mentor. Labs are safe, documented, and designed with student learning in mind.</p>

      <div className="mt-6">
        <h4 className="font-semibold">Skills</h4>
        <div className="mt-2 grid grid-cols-2 md:grid-cols-4 gap-3">
          {skills.map(s => (
            <div key={s.name} className="bg-slate-800/40 p-3 rounded">{s.name}<div className="text-xs text-slate-400">{s.level}</div></div>
          ))}
        </div>
      </div>
    </div>
  )
}


// -----------------------------
// File: src/pages/Contact.jsx
// -----------------------------
import React from 'react'

export default function Contact() {
  return (
    <div>
      <h2 className="text-2xl font-bold">Contact / Join</h2>
      <p className="text-slate-400 mt-2">Join the lab, ask questions, or request a walkthrough.</p>
      <form className="mt-4 grid gap-3 max-w-md">
        <input className="p-3 rounded bg-slate-800/30 border border-slate-700" placeholder="Name" />
        <input className="p-3 rounded bg-slate-800/30 border border-slate-700" placeholder="Email" />
        <textarea className="p-3 rounded bg-slate-800/30 border border-slate-700" placeholder="Message" rows={4}></textarea>
        <button className="btn-cyber">Send</button>
      </form>
    </div>
  )
}


// -----------------------------
// File: src/App.jsx
// -----------------------------
import React from 'react'
import { BrowserRouter, Routes, Route } from 'react-router-dom'
import MainLayout from './layouts/MainLayout'
import Home from './pages/Home'
import Projects from './pages/Projects'
import ProjectDetails from './pages/ProjectDetails'
import About from './pages/About'
import Contact from './pages/Contact'

export default function App() {
  return (
    <BrowserRouter>
      <MainLayout>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/projects" element={<Projects />} />
          <Route path="/projects/:id" element={<ProjectDetails />} />
          <Route path="/about" element={<About />} />
          <Route path="/contact" element={<Contact />} />
        </Routes>
      </MainLayout>
    </BrowserRouter>
  )
}


// -----------------------------
// Notes and next steps
// -----------------------------
// 1) Put real images in public/images and update paths.
// 2) Install packages: run `npm install` then `npm run dev`.
// 3) Tailwind requires PostCSS and tailwind packages already listed.
// 4) This scaffold focuses on teaching UX and interactivity; extend each project folder with safe lab code and README inside each project for students.
