<script setup lang="ts">
// どうぶつしょうぎの最初のならべ方（3 × 4 マス）。上が相手、下が自分。
const ALL = ['n', 'ne', 'e', 'se', 's', 'sw', 'w', 'nw']
const DIAG = ['ne', 'se', 'sw', 'nw']
const CROSS = ['n', 'e', 's', 'w']
const lion = { emoji: '🦁', dirs: ALL }
const elephant = { emoji: '🐘', dirs: DIAG }
const giraffe = { emoji: '🦒', dirs: CROSS }
const chick = { emoji: '🐥', dirs: ['n'] }

const rows = [
  [{ ...giraffe, flip: true }, { ...lion, flip: true }, { ...elephant, flip: true }],
  [null, { ...chick, flip: true }, null],
  [null, chick, null],
  [elephant, lion, giraffe],
]
</script>

<template>
  <div class="board">
    <template v-for="(row, r) in rows" :key="r">
      <div v-for="(cell, c) in row" :key="c" class="cell" :class="{ sky: r === 0, forest: r === 3 }">
        <Piece v-if="cell" :emoji="cell.emoji" :dirs="cell.dirs" :flip="cell.flip" :side="cell.flip ? 'b' : 'a'" :size="74" />
      </div>
    </template>
  </div>
</template>

<style scoped>
.board {
  display: grid; grid-template-columns: repeat(3, 92px); grid-template-rows: repeat(4, 92px);
  border: 4px solid #8a6a3b; border-radius: 10px; overflow: hidden; width: fit-content;
}
.cell { display: grid; place-items: center; background: #fff8e7; border: 1px solid #d9c49a; }
.cell.sky { background: #dff1fb; }
.cell.forest { background: #e4f3d8; }
</style>
