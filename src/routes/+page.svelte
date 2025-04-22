<script>
  import AllBlocks from "$comps/AllBlocks.svelte";
  import meta_img from "$lib/images/meta__img__en.jpg";
  const title = "SIGNALS | Learn trading for free. Make profit every day.";
  const desc =
    "Signals offers powerful, free trading signals and expert guidance for forex traders of all levels. Join Signals for free and access top-tier trading signals, expert guidance, and a supportive community. No experience required! Learn, apply, and grow your trading skills in just 15-20 minutes a day.";
</script>

<svelte:head>
  <title>{title}</title>
  <meta name="description" content="{desc}" />
  <meta property="og:title" content="{title}" />
  <meta property="og:description" content="{desc}" />
  <meta property="og:image" content="{meta_img}" />
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="{title}" />
  <meta name="twitter:description" content="{desc}" />
  <meta name="twitter:image" content="{meta_img}" />
</svelte:head>

<AllBlocks />
