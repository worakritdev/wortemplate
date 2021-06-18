<script>
  export let name, url;
</script>

<div class="p-10 shadow-sm">

    {name}
    {url.split("/")[6]}
    <img
    src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/{url.split(
        '/'
        )[6]}.png"
  class="w-16 h-16"
  />
</div>
  
<style>
  /* your styles go here */
</style>
