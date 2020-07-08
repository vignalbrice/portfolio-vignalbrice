<script>
  import Navbar from "../components/UI/Navbar.svelte";

  let segment;
</script>

<style>

</style>

<Navbar {segment} />

<main>
  <slot />
</main>
