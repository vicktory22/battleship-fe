<script lang="ts">
  export let square: string | undefined;

  function handleClick() {
    square = 'hit';
  }
</script>

<button
  class="w-16 h-16 bg-blue-900 text-white flex items-center justify-center cursor-pointer hover:bg-blue-950"
  on:click={() => handleClick()}
>
  {square}
</button>
