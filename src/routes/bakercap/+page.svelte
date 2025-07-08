<script lang="ts">
  import { ArrowUpRight } from "lucide-svelte";
  import Seo from "$lib/components/Seo.svelte";

  const portfolioCompanies = [
    {
      name: "Clado",
      href: "https://clado.ai/",
      desc: "Deep Research for People.",
      aside: "Backed by Y Combinator, and Baker Capital",
    },
    {
      name: "Shofo",
      href: "https://home.shofo.ai/",
      desc: "The search engine for content.",
      aside: "Backed by Baker Capital",
    },
    {
      name: "Terac",
      href: "https://terac.com/",
      desc: "Automating the exchange of human thoughts through agent-driven market research",
      aside: "Backed by SignalFire, ZFellows, and Baker Capital",
    },
  ];
</script>

<Seo
  title="Zac Baker – BakerCap"
  description="BakerCap - Investment insights and portfolio management."
/>

<section class="layout-md py-12">
  <h2 class="heading2">Portfolio</h2>

  <div class="leading-snug space-y-4">
    {#each portfolioCompanies as company}
      <a class="project-pair" href={company.href}>
        <div class="text-black font-medium">
          {company.name}
          <ArrowUpRight size={18} class="inline text-neutral-400" />
        </div>
        <div>
          <p>{company.desc}</p>
          {#if company.aside}
            <aside>{company.aside}</aside>
          {/if}
        </div>
      </a>
    {/each}
  </div>

  <p class="text-lg mt-8">
    <a class="link" href="/">← Back to Home</a>
  </p>
</section>

<style lang="postcss">
  .project-pair {
    @apply grid sm:grid-cols-[1fr,2fr] gap-y-1 -mx-3 px-3 py-2 hover:bg-neutral-100 transition-colors;
  }

  aside {
    @apply mt-0.5 text-base text-neutral-500;
  }
</style>
