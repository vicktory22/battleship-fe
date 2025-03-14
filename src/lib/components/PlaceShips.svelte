<script lang="ts">
  import { Type, type Static } from '@sinclair/typebox';

  const Point = Type.Object({
    x: Type.Number(),
    y: Type.Number(),
  });

  type Point = Static<typeof Point>;

  const Ship = Type.Object({
    start: Point,
    end: Point,
  });

  const Ships = Type.Object({
    carrier: Ship,
    battleship: Ship,
    cruiser: Ship,
    submarine: Ship,
    destroyer: Ship,
  });

  type Ships = Static<typeof Ships>;

</script>

<div class="grid grid-cols-10 gap-2 my-2 text-blue-700">
  <h3>place ships</h3>
</div>
