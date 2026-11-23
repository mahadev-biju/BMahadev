<script>
  import seleneMoonPreview from './assets/selene-moon-preview.webp';
  import comingSoonSvg from './assets/coming-soon.svg';
  import DotGrid from '$lib/components/DotGrid.svelte';
  import CircularCarousel from '$lib/components/CircularCarousel.svelte';

  let activeProjectIndex = $state(0);

  const projects = [
    {
      src: seleneMoonPreview,
      alt: 'Selene Moon - Lunar Landing Navigator',
      title: 'Selene Moon',
      subtitle: 'A Lunar Landing Navigator, made in Svelte in collaboration with <a href="https://github.com/akshdzn" target="_blank" rel="noopener noreferrer">Akshdzn</a>',
      href: 'https://selenemoon.vercel.app'
    },
    {
      src: comingSoonSvg,
      alt: 'Coming Soon',
      title: 'Coming Soon'
    },
    {
      src: comingSoonSvg,
      alt: 'Coming Soon',
      title: 'Coming Soon'
    },
    {
      src: comingSoonSvg,
      alt: 'Coming Soon',
      title: 'Coming Soon'
    }
  ];

  function scrollToProjects() {
    document.getElementById('projects')?.scrollIntoView({ behavior: 'smooth' });
  }
</script>

<div class="background-grid">
  <DotGrid
    baseColor="#000000"
    activeColor="#ffffff"
    shape="circle"
    dotSize={5}
    gap={14}
    proximity={140}
    strength={0.7}
    bounce={0.5}
    tension={0.5}
    returnDuration={1.4}
    shockRadius={320}
    shockStrength={11}
    swell={0.4}
    stretch={0.2}
    glow={0.9}
    fade={0.5}
    intro
    opacity={0.3}
    mouseInteraction
    clickShock
  />
</div>

<div class="wrapper">
  <!-- First screen (Hero) -->
  <section class="hero-screen">
    <div class="center-content">
      <h1 class="intro-text">Hi! I'm B Mahadev</h1>
    </div>

    <button
      type="button"
      class="scroll-indicator"
      onclick={scrollToProjects}
      aria-label="Scroll for more"
    >
      <span class="scroll-text">scroll for more</span>
      <svg
        class="scroll-chevron"
        width="18"
        height="18"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
      >
        <path d="M7 10l5 5 5-5" />
      </svg>
    </button>
  </section>

  <!-- Projects Section -->
  <section id="projects" class="projects-section">
    <div class="projects-container">
      <h2 class="section-heading">Projects</h2>

      <div class="carousel-container">
        <CircularCarousel
          items={projects}
          preset="cylinder"
          intro="rise"
          cardWidth={576}
          aspectRatio={1.6}
          curve={0}
          gap={44}
          tilt={-4}
          speed={22}
          autoplay="drift"
          interval={3.5}
          direction="left"
          momentum={0.6}
          snap={true}
          pauseOnHover={true}
          focusOnClick={true}
          draggable={true}
          parallax={0.25}
          stretch={0.35}
          fadeColor="#000000"
          depthFade={0.25}
          innerShade={0.5}
          cornerRadius={14}
          captions={false}
          onChange={(index) => (activeProjectIndex = index)}
        />
      </div>

      <div class="project-details">
        {#if projects[activeProjectIndex]?.href}
          <a
            href={projects[activeProjectIndex].href}
            target="_blank"
            rel="noopener noreferrer"
            class="project-title-link"
          >
            <h3 class="project-title">{projects[activeProjectIndex].title}</h3>
            <svg
              class="external-icon"
              width="15"
              height="15"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            >
              <line x1="7" y1="17" x2="17" y2="7"></line>
              <polyline points="7 7 17 7 17 17"></polyline>
            </svg>
          </a>
        {:else}
          <h3 class="project-title">{projects[activeProjectIndex]?.title}</h3>
        {/if}

        {#if projects[activeProjectIndex]?.subtitle}
          <p class="project-subtext">
            {@html projects[activeProjectIndex].subtitle}
          </p>
        {/if}
      </div>
    </div>
  </section>

  <!-- Bottom Social Links / Footer -->
  <footer class="footer">
    <div class="social-links">
      <a
        href="https://github.com/mahadev-biju"
        target="_blank"
        rel="noopener noreferrer"
        class="social-link"
        aria-label="GitHub"
      >
        <svg
          class="social-icon"
          viewBox="0 0 24 24"
          fill="currentColor"
          aria-hidden="true"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.53 1.032 1.53 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
          />
        </svg>
      </a>

      <a
        href="https://www.instagram.com/mahadevbiju_?cnvx=emVsenNtNnV2dG9l"
        target="_blank"
        rel="noopener noreferrer"
        class="social-link"
        aria-label="Instagram"
      >
        <svg
          class="social-icon"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          aria-hidden="true"
        >
          <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
          <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
          <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
        </svg>
      </a>
    </div>
  </footer>
</div>

<style>
  .background-grid {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    height: 100dvh;
    z-index: 0;
    pointer-events: none;
    overflow: hidden;
  }

  .wrapper {
    position: relative;
    z-index: 1;
    width: 100%;
    min-height: 100vh;
    background-color: transparent;
  }

  .hero-screen {
    position: relative;
    width: 100%;
    height: 100vh;
    height: 100dvh;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
  }

  .center-content {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 1.5rem;
  }

  .intro-text {
    margin: 0;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
    font-size: clamp(2.2rem, 5.5vw, 4.2rem);
    font-weight: 700;
    color: #0f172a;
    letter-spacing: -0.03em;
    line-height: 1.2;
    user-select: none;
    animation: appear 0.75s cubic-bezier(0.16, 1, 0.3, 1) both;
  }

  .scroll-indicator {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.35rem;
    background: none;
    border: none;
    padding: 0.5rem 1rem;
    cursor: pointer;
    color: #888888;
    transition: color 0.2s ease;
    animation: fadeIn 0.8s ease-out 0.4s both;
  }

  .scroll-indicator:hover {
    color: #111111;
  }

  .scroll-text {
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.04em;
    text-transform: lowercase;
    user-select: none;
  }

  .scroll-chevron {
    animation: bounce 1.8s infinite ease-in-out;
  }

  .projects-section {
    min-height: 100vh;
    min-height: 100dvh;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 4rem 1.5rem 5rem;
    border-top: 1px solid rgba(0, 0, 0, 0.06);
  }

  .projects-container {
    width: 100%;
    max-width: 1320px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .section-heading {
    font-size: clamp(1.6rem, 3vw, 2.2rem);
    font-weight: 700;
    color: #0f172a;
    margin: 0 0 1.5rem 0;
    letter-spacing: -0.02em;
    text-align: center;
  }

  .carousel-container {
    width: 100%;
    height: 720px;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .project-details {
    margin-top: 1.25rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 0.35rem;
  }

  .project-title-link {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    text-decoration: none;
    color: #111111;
    width: fit-content;
    transition: color 0.15s ease;
  }

  .project-title-link:hover {
    color: #0066cc;
  }

  .project-title {
    margin: 0;
    font-size: clamp(1.05rem, 1.8vw, 1.25rem);
    font-weight: 700;
    letter-spacing: -0.01em;
  }

  .external-icon {
    transition: transform 0.2s ease;
  }

  .project-title-link:hover .external-icon {
    transform: translate(2px, -2px);
  }

  .project-subtext {
    margin: 0;
    font-size: 0.92rem;
    color: #666666;
    line-height: 1.45;
  }

  .project-subtext :global(a) {
    color: #0066cc;
    text-decoration: underline;
    text-underline-offset: 2px;
    transition: color 0.15s ease;
  }

  .project-subtext :global(a:hover) {
    color: #004499;
  }

  @keyframes appear {
    0% {
      opacity: 0;
      transform: translateY(10px);
      filter: blur(3px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
      filter: blur(0);
    }
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translate(-50%, 8px);
    }
    to {
      opacity: 1;
      transform: translate(-50%, 0);
    }
  }

  @keyframes bounce {
    0%, 100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(5px);
    }
  }

  .footer {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2.5rem 1.5rem 3rem;
    width: 100%;
  }

  .social-links {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 1.5rem;
  }

  .social-link {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 0.5rem;
    color: #71717a;
    border-radius: 10px;
    text-decoration: none;
    transition: color 0.2s ease, transform 0.2s ease;
  }

  .social-link:hover {
    color: #0f172a;
    transform: translateY(-3px);
  }

  .social-icon {
    width: 40px;
    height: 40px;
    display: block;
  }
</style>
