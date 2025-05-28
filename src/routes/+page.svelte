<script lang="ts">
  import { ArrowUpRight } from "lucide-svelte";

  import Seo from "$lib/components/Seo.svelte";

  const featuredProjects = [
      {
      name: "Radical Health",
      href: "https://radicalhealth.ai/",
      desc: "Founding engineer building foudnation models for cancer",
      aside: "2025-Present, backed by Khosla, partnered with Mayo Clinic",
    },
    {
      name: "MIT CSAIL",
      href: "https://www.csail.mit.edu/",
      desc: "Trained foundation audio and video models",
      aside: "2024-Present",
    },
    {
      name: "UCL RPL",
      href: "https://rpl-as-ucl.github.io/",
      desc: "Taught robots to think",
      aside: "2024-2025",
    },
    {
      name: "University College London",
      href: "https://www.ucl.ac.uk/",
      desc: "University",
      aside: "2024-Dropped out",
    },
    {
      name: "Zeed",
      href: "https://zeed.ai/",
      desc: "Founding engineer, scaled from $0-$10M+",
      aside: "2021-2023",
    },
    {
      name: "TJHSST",
      href: "https://tjhsst.edu",
      desc: "High school",
      aside: "2020-2024",
    },
  ]

</script>

<Seo
  title="Zac Baker"
  description="Researcher, engineer, and doer. Making meaningful systems and interfaces for people."
/>

<p
  class="layout-md text-black text-xl leading-tight font-light mb-16"
  id="eric-is"
>
  <span class="g">is a</span> ML researcher<span class="g">,</span><br />
  engineer<span class="g">, and</span><br />
  learner<span class="g">.</span>
</p>

<div class="layout-md text-lg space-y-14">
  <div class="space-y-5">
    <p>
      I currently work at <a class="link" href="https://radicalhealth.ai/">Radical</a>, training foundational models for cancer.
    </p>

    <p>
      I want to build an <em>autonomous world</em> for people to be able to live their most fulfilling lives.
    </p>

    <p>
      Towards that goal, I am a generalist and care deeply about building <em>systems</em
      >, which will move society towards a more fulfilling future.
    </p>
  </div>

  <div class="leading-snug space-y-4">
    <p class="pb-2">What I've done:</p>

    {#each featuredProjects as project}
      <a class="project-pair" href={project.href}>
        <div class="text-black font-medium">
          {project.name}
          <ArrowUpRight size={18} class="inline text-neutral-400" />
        </div>
        <div>
          <p>{project.desc}</p>
          {#if project.aside}
            <aside>{project.aside}</aside>
          {/if}
        </div>
      </a>
    {/each}
  </div>

  <div class="space-y-5">


    <p>Other interests: math, outdoors.</p>
  </div>

</div>

<style lang="postcss">
  .g {
    @apply text-neutral-400;
  }

  em {
    @apply font-serif text-[110%] leading-[100%];
  }

  .project-pair {
    @apply grid sm:grid-cols-[1fr,2fr] gap-y-1 -mx-3 px-3 py-2 hover:bg-neutral-100 transition-colors;
  }

  aside {
    @apply mt-0.5 text-base text-neutral-500;
  }

  /* Correction for vertical navigation links on mobile. */
  @media (max-width: 420px) {
    #eric-is {
      @apply -mt-10;
    }
  }
</style>
