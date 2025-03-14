<script lang="ts">
  import BoardSquare from "./BoardSquare.svelte";

  export let board: string[][];
</script>

<div class="grid grid-cols-10 gap-2 my-2">
  {#each board as row, rowIndex}
    {#each row as _, colIndex}
      <BoardSquare bind:square={board[rowIndex][colIndex]} />
    {/each}
  {/each}
</div>
