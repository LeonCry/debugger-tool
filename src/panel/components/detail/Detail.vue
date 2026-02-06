<script setup lang="ts">
import { IconX } from '@tabler/icons-vue';

const props = defineProps<{
  row: Record<string, any> | null
  height: number
}>();
const emits = defineEmits<{ 'update:row': [Record<string, any> | null] }>();
const row = useVModel(props, 'row', emits);
function close() {
  row.value = null;
}
</script>

<template>
  <section class="detail-container" :style="{ height: `${height}px` }">
    <RoundButton class="p-1! top-0 right-0 absolute" @click="close">
      <IconX :size="14" />
    </RoundButton>
    <div v-for="(value, key) in row || {}" :key="key" class="flex">
      <div>
        {{ key }} : {{ value }}
      </div>
    </div>
  </section>
</template>

<style scoped>
.detail-container {
  padding: 4px;
  position: relative;
  border-radius: 12px;
  box-shadow:
    4px 4px 8px var(--btn_shadow_r),
    -4px -4px 8px var(--btn_shadow_l);
}
</style>
