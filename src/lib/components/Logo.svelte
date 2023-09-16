<script lang="ts">
  import Link from "./Link.svelte";

  export let link: string;
  export let logo: string;
  export let name: string;
</script>

<Link href={link}>
  <img
    class="w-10 h-10 p-1.5 rounded-md shadow-[5px_5px_rgb(88,_28,_135,_0.4)]"
    src={logo}
    alt="Logo of {name}"
  />
</Link>
