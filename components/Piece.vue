<script setup lang="ts">
// 駒 1 個。dirs に動ける向き（n, ne, e, se, s, sw, w, nw）を渡すと、ふちに点を打つ。
// flip を付けると相手側の駒として 180° 回る。
withDefaults(defineProps<{
  emoji: string
  name?: string
  dirs?: string[]
  flip?: boolean
  side?: 'a' | 'b'
  size?: number
}>(), { dirs: () => [], flip: false, side: 'a', size: 84 })
</script>

<template>
  <div class="piece-wrap">
    <div
      class="piece"
      :class="[`side-${side}`, { flip }]"
      :style="{ width: `${size}px`, height: `${size}px`, fontSize: `${size * 0.5}px` }"
    >
      <span class="emoji">{{ emoji }}</span>
      <i v-for="d in dirs" :key="d" class="dot" :class="`d-${d}`" />
    </div>
    <div v-if="name" class="piece-name">{{ name }}</div>
  </div>
</template>

<style scoped>
.piece-wrap { display: inline-flex; flex-direction: column; align-items: center; gap: 6px; }
.piece {
  position: relative; display: grid; place-items: center;
  border-radius: 14%; border: 3px solid #b98a4b; background: #fbe9c6;
  box-shadow: 0 3px 0 #b98a4b; line-height: 1;
}
.piece.side-b { background: #d9efd0; border-color: #6f9a5c; box-shadow: 0 3px 0 #6f9a5c; }
.piece.flip { transform: rotate(180deg); }
.dot { position: absolute; width: 11%; height: 11%; border-radius: 50%; background: #e0452c; }
.d-n  { top: 5%; left: 44.5%; }
.d-s  { bottom: 5%; left: 44.5%; }
.d-w  { left: 5%; top: 44.5%; }
.d-e  { right: 5%; top: 44.5%; }
.d-nw { top: 5%; left: 5%; }
.d-ne { top: 5%; right: 5%; }
.d-sw { bottom: 5%; left: 5%; }
.d-se { bottom: 5%; right: 5%; }
.piece-name { font-size: 16px; font-weight: 700; }
</style>
