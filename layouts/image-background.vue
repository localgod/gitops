<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  background: {
    default: undefined,
  },
})

function resolveAssetUrl(url: string) {
  if (url?.startsWith('/'))
    return import.meta.env.BASE_URL + url.slice(1)
  return url
}

const style = computed(() => {
  if (!props.background) return {}
  
  const isColor = props.background && ['#', 'rgb', 'hsl'].some(v => props.background.indexOf(v) === 0)
  
  return {
    background: isColor ? props.background : undefined,
    backgroundImage: isColor ? undefined : `url("${resolveAssetUrl(props.background)}")`,
    backgroundRepeat: 'no-repeat',
    backgroundPosition: 'center',
    backgroundSize: 'cover',
  }
})
</script>

<template>
  <div class="slidev-layout default" :style="style">
    <slot />
  </div>
</template>
