<script lang="ts">
  import Board from "$lib/components/Board.svelte";
  import PlaceShips from "$lib/components/PlaceShips.svelte";

  const config = {
    board: {
      length: 10,
    },
  };

  let game = $state({
    stage: "creating",
    player1: {
      placedShips: false,
      ships: {
        carrier: {
          start: undefined,
          end: undefined,
        },
        battleship: {
          start: undefined,
          end: undefined,
        },
        cruiser: {
          start: undefined,
          end: undefined,
        },
        submarine: {
          start: undefined,
          end: undefined,
        },
        destroyer: {
          start: undefined,
          end: undefined,
        },
      },
    },
    player2: {
      placeShips: false,
      ships: {
        carrier: {
          start: undefined,
          end: undefined,
        },
        battleship: {
          start: undefined,
          end: undefined,
        },
        cruiser: {
          start: undefined,
          end: undefined,
        },
        submarine: {
          start: undefined,
          end: undefined,
        },
        destroyer: {
          start: undefined,
          end: undefined,
        },
      },
    },
    board: Array(config.board.length).fill(
      Array(config.board.length).fill(undefined),
    ),
  });
</script>

<div class="flex flex-col items-center">
  <h1 class="text-2xl font-bold my-4 text-blue-700">Battleship Game</h1>

  <div>
    <h2 class="text-lg font-semibold text-blue-700">Player 1 Board</h2>
    {#if game.player1.placedShips}
      <PlaceShips bind:ships={game.player1.ships} />
    {:else}
      <Board bind:board={game.board} />
    {/if}
  </div>

  <div>
    <h2 class="text-lg font-semibold text-blue-700 pt-8">Player 2 Board</h2>
    <Board bind:board={game.board} />
  </div>
</div>
