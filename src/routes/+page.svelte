<script lang="ts">
  import { resume } from "$lib/stores";
  import Highlights from "$lib/components/Highlights.svelte";
  import Education from "$lib/components/Education.svelte";
  import Experience from "$lib/components/Experience.svelte";
  import Header from "$lib/components/Header.svelte";
  import Navigation from "$lib/components/Navigation.svelte";
  import Projects from "$lib/components/Projects.svelte";
  import Skills from "$lib/components/Skills.svelte";

  const width = 1000;
  // TODO fix aspect ratio bug: (#1)
  const ratio = Math.SQRT1_2 * 1.001;

  $resume = $$props.data.resume as Resume;
</script>

<svelte:head>
  <title>{$resume.meta.title}</title>
</svelte:head>

<main
  style="width: {width}px;"
  class="overflow-hidden mx-auto bg-white"
>
  <Header />

  <Navigation />

  <div class="p-6 space-y-6">
    <Experience />

    <Education />

    <Projects />

    <div class="grid grid-cols-2 gap-7">
      <Highlights />

      <Skills />
    </div>
  </div>
</main>

<style lang="postcss">
  @media print {
    main {
      @apply my-0 shadow-none rounded-none;
    }
  }
</style>
