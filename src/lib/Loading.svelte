<script>
  import { onMount } from 'svelte';
  import saoVideo from './sao.mp4';

  let {
    src = saoVideo,
    alt = "Animated clip",
    onended,
    onfinish
  } = $props();

  let videoElement = $state();
  let isFading = $state(false);

  function handleVideoEnded() {
    if (isFading) return;
    isFading = true;
    onended?.();
    setTimeout(() => {
      onfinish?.();
    }, 450);
  }

  onMount(() => {
    if (videoElement) {
      videoElement.play().catch((err) => {
        console.warn("Autoplay was prevented:", err);
      });
    }
  });
</script>

<div class="video-container" class:fade-out={isFading}>
  <video
    bind:this={videoElement}
    {src}
    autoplay
    muted
    playsinline
    aria-label={alt}
    class="anim-video"
    onended={handleVideoEnded}
    onerror={handleVideoEnded}
  ></video>
</div>

<style>
  .video-container {
    position: fixed;
    inset: 0;
    width: 100vw;
    height: 100vh;
    height: 100dvh;
    overflow: hidden;
    background-color: #000000;
    transition: opacity 0.45s ease-out;
    z-index: 100;
  }

  .video-container.fade-out {
    opacity: 0;
    pointer-events: none;
  }

  .anim-video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }
</style>
