<script>
  import { base } from "$app/paths";
  import IntroVideo from "./IntroVideo.svelte";
  import IntroList from "./IntroList.svelte";
  import "./scss/intro.scss";
</script>

<header>
  <img
    src="{base}/images/logo_dark.webp"
    width="157px"
    height="35px"
    alt="Logotype"
  />
  <a href="#" class="button">
    <span>Start Trading for FREE</span>
  </a>
</header>
<section class="intro">
  <img src="{base}/images/tab.webp" alt="" width="190px" height="37px" />
  <h1>COPY OUR TRADES FOR <span>FREE</span></h1>

  <h2>Make Money from your phone anywhere, at any time!</h2>
  <a href="#" class="button">
    <span>Join Our FREE Trading Group</span>
  </a>
  <IntroVideo />
  <IntroList />
</section>
