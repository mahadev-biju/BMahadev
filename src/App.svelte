<script>
  import seleneMoonPreview from './assets/selene-moon-preview.webp';

  function scrollToProjects() {
    document.getElementById('projects')?.scrollIntoView({ behavior: 'smooth' });
  }
</script>

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

      <div class="project-card">
        <a
          href="https://selenemoon.vercel.app"
          target="_blank"
          rel="noopener noreferrer"
          class="project-preview-link"
        >
          <div class="image-wrapper">
            <img
              src={seleneMoonPreview}
              alt="Preview of selenemoon.vercel.app - Lunar Landing Navigator"
              class="preview-img"
              loading="lazy"
            />
            <div class="hover-overlay">
              <span class="view-pill">
                Visit Website
                <svg
                  width="13"
                  height="13"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2.2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                  <polyline points="15 3 21 3 21 9"></polyline>
                  <line x1="10" y1="14" x2="21" y2="3"></line>
                </svg>
              </span>
            </div>
          </div>
        </a>

        <div class="project-details">
          <a
            href="https://selenemoon.vercel.app"
            target="_blank"
            rel="noopener noreferrer"
            class="project-title-link"
          >
            <h3 class="project-title">Selene Moon</h3>
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
          <p class="project-subtext">A Lunar Landing Navigator</p>
        </div>
      </div>
    </div>
  </section>
</div>

<style>
  .wrapper {
    width: 100%;
    min-height: 100vh;
    background-color: #ffffff;
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
    color: #111111;
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
    border-top: 1px solid #f0f0f0;
  }

  .projects-container {
    width: 100%;
    max-width: 520px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .section-heading {
    font-size: clamp(1.6rem, 3vw, 2.2rem);
    font-weight: 700;
    color: #111111;
    margin: 0 0 2rem 0;
    letter-spacing: -0.02em;
    text-align: center;
  }

  .project-card {
    width: 100%;
    background-color: #ffffff;
    border: 1px solid #e8e8e8;
    border-radius: 14px;
    overflow: hidden;
    transition:
      transform 0.3s cubic-bezier(0.16, 1, 0.3, 1),
      box-shadow 0.3s cubic-bezier(0.16, 1, 0.3, 1),
      border-color 0.3s ease;
    box-shadow: 0 4px 18px rgba(0, 0, 0, 0.04);
  }

  .project-card:hover {
    transform: translateY(-4px);
    border-color: #cfcfcf;
    box-shadow: 0 14px 30px rgba(0, 0, 0, 0.09);
  }

  .project-preview-link {
    display: block;
    text-decoration: none;
    overflow: hidden;
  }

  .image-wrapper {
    position: relative;
    width: 100%;
    background-color: #0b0c10;
    overflow: hidden;
    aspect-ratio: 16 / 10;
  }

  .preview-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
  }

  .project-card:hover .preview-img {
    transform: scale(1.025);
  }

  .hover-overlay {
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.28);
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 0;
    transition: opacity 0.25s ease;
    backdrop-filter: blur(2px);
  }

  .project-card:hover .hover-overlay {
    opacity: 1;
  }

  .view-pill {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    padding: 0.55rem 1.1rem;
    background-color: rgba(255, 255, 255, 0.95);
    color: #111111;
    font-size: 0.85rem;
    font-weight: 600;
    border-radius: 9999px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
  }

  .project-details {
    padding: 1.25rem 1.4rem;
    display: flex;
    flex-direction: column;
    gap: 0.35rem;
    background: #ffffff;
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
</style>
