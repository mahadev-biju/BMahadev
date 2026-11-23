<script>
  import saoVideo from './sao.mp4';

  let { src = saoVideo, alt = "Animated clip" } = $props();
</script>

<div class="video-container">
  <video
    {src}
    autoplay
    muted
    playsinline
    aria-label={alt}
    class="anim-video"
  ></video>
</div>

<style>
  .video-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    background-color: #000;
  }

  .anim-video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }
</style>
