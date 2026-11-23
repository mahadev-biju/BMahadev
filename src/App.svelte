<script>
  import Loading from './lib/Loading.svelte';

  let isAnimationEnded = $state(false);
  let showLoading = $state(true);

  function handleEnded() {
    isAnimationEnded = true;
  }

  function handleFinish() {
    showLoading = false;
  }
</script>

<main class="page-container">
  {#if showLoading}
    <Loading onended={handleEnded} onfinish={handleFinish} />
  {/if}

  {#if isAnimationEnded}
    <div class="center-content">
      <h1 class="intro-text">Hi! I'm B Mahadev</h1>
    </div>
  {/if}
</main>

<style>
  .page-container {
    width: 100%;
    height: 100%;
    min-height: 100vh;
    min-height: 100dvh;
    background-color: #ffffff;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    overflow: hidden;
  }

  .center-content {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 1.5rem;
    animation: fadeIn 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  }

  .intro-text {
    margin: 0;
    font-size: clamp(2.2rem, 6vw, 4.5rem);
    font-weight: 700;
    color: #111111;
    letter-spacing: -0.02em;
    line-height: 1.2;
    user-select: none;
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(12px) scale(0.98);
    }
    to {
      opacity: 1;
      transform: translateY(0) scale(1);
    }
  }
</style>
