<script>
  const items = [
    {
      title: "1000+",
      caption: "EMPOWERED TRADERS",
    },
    { title: "98%", caption: "TRADERS SATISFACTION" },
    { title: "$1.5M+", caption: "PROFIT AND COUNTING" },
    { title: "100%", caption: "FREE TO JOIN AND LEARN" },
  ];
</script>

<ul class="intro-list">
  {#each items as item}
    <li class="intro-list-item">
      <div class="intro-list-title">{item.title}</div>
      <div class="intro-list-caption">{item.caption}</div>
    </li>
  {/each}
</ul>
