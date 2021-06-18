<script>
  // your script goes here

  import Header from "./components/Header.svelte";
  import SideMenu from "./components/SideMenu.svelte";
  import SearchBox from "./controller/SearchBox.svelte";
  export let name;
</script>

<!-- markup (zero or more items) goes here -->
{name}
<SearchBox />

<style>
</style>
