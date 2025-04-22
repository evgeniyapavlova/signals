<script>
  import { onMount } from "svelte";
  import { base } from "$app/paths";

  let videoElement,
    isPlaying = false,
    firstPlay = false,
    progress = 0;

  const togglePlay = () => {
    if (!videoElement) return;
    if (videoElement.paused) {
      videoElement.play();
    } else {
      videoElement.pause();
    }
    isPlaying = !videoElement.paused;
  };

  onMount(() => {
    if (videoElement) {
      videoElement.addEventListener("play", () => {
        if (!firstPlay) firstPlay = true;
        isPlaying = true;
      });
      videoElement.addEventListener("pause", () => (isPlaying = false));
    }
  });

  const updateProgress = () => {
    if (videoElement?.duration) {
      progress = (videoElement.currentTime / videoElement.duration) * 100;
    }
  };

  const seek = (event) => {
    const bar = event.currentTarget;
    const rect = bar.getBoundingClientRect();
    const clickX = event.clientX - rect.left;
    const percent = clickX / rect.width;
    videoElement.currentTime = percent * videoElement.duration;
  };
</script>

<div class="intro-video {firstPlay && 'intro-video-started'}">
  <div class="intro-video-poster">
    <picture>
      <source srcset="{base}/images/base_chart.avif" type="image/avif" />
      <source srcset="{base}/images/base_chart.webp" type="image/webp" />
      <img src="{base}/images/base_chart.png" alt="VIP terms trading" />
    </picture>
  </div>
  <video
    bind:this="{videoElement}"
    preload="auto"
    on:timeupdate="{updateProgress}"
  >
    <source src="{base}/video/video.mp4" type="video/mp4" />
    <track kind="captions" />
  </video>

  <button class="progress-bar" on:click="{seek}">
    <div class="progress-filled" style="width: {progress}%"></div>
  </button>

  <button
    on:click="{togglePlay}"
    class="control-button control-button-{isPlaying ? 'play' : 'pause'}"
  >
    <img
      src="{base}/images/pause.svg"
      alt="pause"
      class="{isPlaying ? 'control-visible' : 'control-hidden'}"
    />
    <img
      src="{base}/images/play.svg"
      alt="play"
      class="{isPlaying ? 'control-hidden' : 'control-visible'}"
    />
  </button>
</div>
