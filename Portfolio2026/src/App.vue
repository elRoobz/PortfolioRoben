<template>
  <!-- NAVIGATION -->
  <nav>
    <div class="nav-inner">
      <a href="#" class="nav-name">ROOBZ</a>
      <ul class="nav-links">
        <li><a href="#about" @click.prevent="scrollTo('about')">About</a></li>
        <li><a href="#projects" @click.prevent="scrollTo('projects')">Projects</a></li>
        <li><a href="#video" @click.prevent="scrollTo('video')">Video CV</a></li>
        <li><a href="#contact" @click.prevent="scrollTo('contact')">Contact</a></li>
      </ul>
      <button class="hamburger" @click="menuOpen = !menuOpen" aria-label="Menu">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
    <div class="mobile-menu" :class="{ open: menuOpen }">
      <a href="#about" @click="scrollTo('about'); menuOpen = false">About</a>
      <a href="#projects" @click="scrollTo('projects'); menuOpen = false">Projects</a>
      <a href="#video" @click="scrollTo('video'); menuOpen = false">Video CV</a>
      <a href="#contact" @click="scrollTo('contact'); menuOpen = false">Contact</a>
    </div>
  </nav>

  <!-- HERO / ABOUT -->
  <section id="about">
    <div class="hero">
      <div class="hero-text">
        <h1>Roben Eid</h1>
        <p>
          Multimedia Design student. I work with visual communication, web development,
          and digital content. This is a selection of projects from my studies.
        </p>
        <div class="hero-links">
          <a href="cv/Blue Light Blue Color Blocks Flight Attendant CV.pdf" class="btn btn-filled" target="_blank">Download CV</a>
          <a href="https://www.linkedin.com/in/roben-eid-870465291/" class="btn" target="_blank">LinkedIn</a>
        </div>
      </div>
      <!-- Replace src with your actual photo path, e.g. /images/profile/photo.jpg -->
      <!-- <img src="/images/profile/photo.jpg" alt="Roben M." class="hero-photo" /> -->
      <div class="hero-photo-placeholder"><img src="/images/profile/att.9gVU1YZUNFLbQe_i0y62zHReMym-KisUGeIFZcmLucg.JPG" alt="Roben M." class="hero-photo"/></div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card" v-for="project in projects" :key="project.id">
        <!-- If you have a screenshot, replace the placeholder with:
             <img :src="project.image" :alt="project.title" class="project-img" />
        -->
        <div class="project-img-placeholder" v-if="!project.image">
          Screenshot / image
        </div>
        <img
          v-else
          :src="project.image"
          :alt="project.title"
          class="project-img"
        />
        <div class="project-body">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
        </div>
      </div>
    </div>
  </section>

  <!-- VIDEO CV -->
  <section id="video">
    <h2>Video CV</h2>
    <p>A short video introduction.</p>
    <div class="video-wrapper" style="margin-top: 20px;">
      <iframe
        src="https://www.youtube.com/embed/nELE9dyPN6o"
        title="Video CV"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      ></iframe>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <h2>Contact</h2>
    <ul class="contact-list">
      <li>Email: <a href="mailto:your@email.com">robendudeofficial@gmail.com</a></li>
      <li>LinkedIn: <a href="https://www.linkedin.com/in/roben-eid-870465291/" target="_blank">linkedin.com/in/roben-eid-870465291/</a></li>
      <li>CV: <a href="cv/Blue Light Blue Color Blocks Flight Attendant CV.pdf" target="_blank">Download PDF</a></li>
    </ul>
  </section>

  <footer>
    Roben Eid  &mdash; Portfolio
  </footer>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
      projects: [
        {
          id: 1,
          title: 'MiniMe',
          image: '/images/projects/MiniMe.png',
          // To add a screenshot: image: '/images/projects/minime.jpg',
          description:
            'A mini character version of myself, created as my first project in Content Creation. The character is drawn in a cartoon style inspired by South Park — bold shapes, minimal detail, and a clear silhouette.'
        },
        {
          id: 2,
          title: 'INT Poster Day',
          image: '/images/projects/INTdayposter.png',
          // image: '/images/projects/int-poster.jpg',
          description:
            'A poster designed for an International Day event at school. The goal was to attract attention, inform students about the event, and build excitement around the celebration of different cultures and cuisines.'
        },
        {
          id: 3,
          title: 'Recipe Website',
          image: '/images/projects/recipewebsite.png',
          // image: '/images/projects/recipe.jpg',
          description:
            'A recipe website built as a mandatory web development assignment. The site lets users browse recipes in an organized way. The focus was on combining layout, structure, and usability using core front-end techniques.'
        },
        {
          id: 4,
          title: 'Brødrene Løvehjerte',
          image: '/images/projects/brødreneproject.png',
          // image: '/images/projects/broedrene.jpg',
          description:
            'A website made to promote a theatre performance of Brødrene Løvehjerte by Skarntyden. The site was designed to spread awareness about the show, share practical information, and draw an audience to the event.'
        },
        {
          id: 5,
          title: 'EASV Event Ticket App',
          image: '/images/projects/Eventmanager.png',
          // image: '/images/projects/easv-ticket.jpg',
          description:
            'An event ticket app created for EASV (SEA). The app was built to make it easier to manage and book tickets for school events, providing a digital alternative to manual registration.'
        }
      ]
    };
  },
  methods: {
    scrollTo(id) {
      const el = document.getElementById(id);
      if (el) {
        el.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
};
</script>

<style>
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

:root {
  --black: #111;
  --white: #fff;
  --gray: #555;
  --light-gray: #e8e8e8;
  --bg: #f9f9f9;
  --accent: #222;
}

body {
  font-family: 'Georgia', serif;
  background-color: var(--bg);
  color: var(--black);
  line-height: 1.6;
}

a {
  color: var(--black);
  text-decoration: underline;
}

a:hover {
  color: var(--gray);
}

/* NAV */
nav {
  border-bottom: 1px solid var(--light-gray);
  background: var(--white);
  position: sticky;
  top: 0;
  z-index: 100;
}

.nav-inner {
  max-width: 960px;
  margin: 0 auto;
  padding: 0 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 56px;
}

.nav-name {
  font-size: 1rem;
  font-weight: bold;
  text-decoration: none;
  color: var(--black);
}

.nav-links {
  display: flex;
  gap: 28px;
  list-style: none;
}

.nav-links a {
  text-decoration: none;
  font-size: 0.9rem;
  color: var(--gray);
}

.nav-links a:hover {
  color: var(--black);
}

.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
  background: none;
  border: none;
  padding: 4px;
}

.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--black);
}

.mobile-menu {
  display: none;
  flex-direction: column;
  background: var(--white);
  border-bottom: 1px solid var(--light-gray);
  padding: 16px 24px;
  gap: 14px;
}

.mobile-menu.open {
  display: flex;
}

.mobile-menu a {
  text-decoration: none;
  font-size: 0.95rem;
  color: var(--gray);
}

/* SECTIONS */
section {
  max-width: 960px;
  margin: 0 auto;
  padding: 72px 24px;
}

section + section {
  border-top: 1px solid var(--light-gray);
}

h1 {
  font-size: 2rem;
  font-weight: bold;
  margin-bottom: 12px;
  line-height: 1.2;
}

h2 {
  font-size: 1.4rem;
  font-weight: bold;
  margin-bottom: 32px;
  letter-spacing: 0.02em;
}

h3 {
  font-size: 1.1rem;
  font-weight: bold;
  margin-bottom: 10px;
}

p {
  color: var(--gray);
  font-size: 0.95rem;
  max-width: 600px;
}

/* HERO */
.hero {
  display: flex;
  align-items: center;
  gap: 48px;
  flex-wrap: wrap;
}

.hero-text {
  flex: 1;
  min-width: 240px;
}

.hero-text h1 {
  margin-bottom: 16px;
}

.hero-text p {
  margin-bottom: 24px;
}

.hero-links {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.btn {
  display: inline-block;
  padding: 10px 22px;
  font-size: 0.85rem;
  text-decoration: none;
  border: 1px solid var(--black);
  color: var(--black);
  background: transparent;
  cursor: pointer;
  font-family: inherit;
  transition: background 0.15s, color 0.15s;
}

.btn:hover {
  background: var(--black);
  color: var(--white);
}

.btn-filled {
  background: var(--black);
  color: var(--white);
}

.btn-filled:hover {
  background: var(--gray);
  border-color: var(--gray);
}

.hero-photo {
  width: 180px;
  height: 180px;
  object-fit: cover;
  border: 1px solid var(--light-gray);
  flex-shrink: 0;
}

.hero-photo-placeholder {
  width: 180px;
  height: 180px;
  background: var(--light-gray);
  border: 1px solid #ddd;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  color: #999;
  flex-shrink: 0;
}

/* PROJECTS */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 32px;
}

.project-card {
  border: 1px solid var(--light-gray);
  background: var(--white);
}

.project-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  display: block;
}

.project-img-placeholder {
  width: 100%;
  height: 200px;
  background: var(--light-gray);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  color: #999;
}

.project-body {
  padding: 20px;
}

.project-body h3 {
  margin-bottom: 8px;
}

.project-body p {
  font-size: 0.88rem;
  color: var(--gray);
  max-width: 100%;
}

/* VIDEO */
.video-wrapper {
  margin-top: 16px;
}

.video-wrapper iframe {
  width: 100%;
  max-width: 640px;
  height: 360px;
  border: 1px solid var(--light-gray);
}

.video-placeholder {
  width: 100%;
  max-width: 640px;
  height: 200px;
  background: var(--light-gray);
  border: 1px solid #ddd;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.85rem;
  color: #999;
}

/* CONTACT */
.contact-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 8px;
}

.contact-list li {
  font-size: 0.9rem;
  color: var(--gray);
}

.contact-list a {
  color: var(--black);
}

/* FOOTER */
footer {
  border-top: 1px solid var(--light-gray);
  text-align: center;
  padding: 28px 24px;
  font-size: 0.8rem;
  color: #aaa;
}

/* RESPONSIVE */
@media (max-width: 640px) {
  h1 {
    font-size: 1.5rem;
  }

  .hero {
    flex-direction: column-reverse;
    align-items: flex-start;
    gap: 24px;
  }

  .nav-links {
    display: none;
  }

  .hamburger {
    display: flex;
  }

  section {
    padding: 48px 20px;
  }

  .video-wrapper iframe {
    height: 220px;
  }
}
</style>
