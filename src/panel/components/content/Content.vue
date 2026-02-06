<script setup lang="ts">
import { IconCopyrightFilled, IconLocationFilled, IconLockFilled } from '@tabler/icons-vue';

defineProps<{ height: number, checkDetail: (row: Record<string, any>) => void }>();

const columns = [
  { field: 'status', label: 'STATUS', minWidth: '12%' },
  { field: 'type', label: 'TYPE', minWidth: '10%' },
  { field: 'size', label: 'SIZE', minWidth: '10%' },
  { field: 'time', label: 'TIME', minWidth: '10%' },
];
const tableData = [
  {
    name: 'file1.txt',
    status: '200',
    type: 'text',
    size: '100KB',
    time: '12ms',
  },
  {
    name: 'file2.jpg',
    status: '404',
    type: 'image',
    size: '200KB',
    time: '2ms',
  },
  {
    name: 'file3.png',
    status: '200',
    type: 'image',
    size: '300KB',
    time: '3ms',
  },
  {
    name: 'file4.json',
    status: '200',
    type: 'json',
    size: '400KB',
    time: '4ms',
  },
  {
    name: 'file5.xml',
    status: '200',
    type: 'xml',
    size: '500KB',
    time: '5ms',
  },
  {
    name: 'file6.html',
    status: '200',
    type: 'html',
    size: '600KB',
    time: '6ms',
  },
  {
    name: 'file7.css',
    status: '200',
    type: 'css',
    size: '700KB',
    time: '7ms',
  },
  {
    name: 'file8.js',
    status: '200',
    type: 'js',
    size: '800KB',
    time: '8ms',
  },
  {
    name: 'file9.txt',
    status: '200',
    type: 'text',
    size: '900KB',
    time: '9ms',
  },
  {
    name: 'file10.jpg',
    status: '200',
    type: 'image',
    size: '1000KB',
    time: '10ms',
  },
  {
    name: 'file11.png',
    status: '200',
    type: 'image',
    size: '1100KB',
    time: '11ms',
  },
  {
    name: 'file12.txt',
    status: '200',
    type: 'text',
    size: '1200KB',
    time: '12ms',
  },
  {
    name: 'file13.png',
    status: '200',
    type: 'image',
    size: '1300KB',
    time: '13ms',
  },
  {
    name: 'file14.png',
    status: '200',
    type: 'image',
    size: '1400KB',
    time: '14ms',
  },
  {
    name: 'file15.png',
    status: '200',
    type: 'image',
    size: '1500KB',
    time: '15ms',
  },
  {
    name: 'file16.png',
    status: '200',
    type: 'image',
    size: '1600KB',
    time: '16ms',
  },
  {
    name: 'file17.png',
    status: '200',
    type: 'image',
    size: '1700KB',
    time: '17ms',
  },
  {
    name: 'file18.png',
    status: '200',
    type: 'image',
    size: '1800KB',
    time: '18ms',
  },
  {
    name: 'file19.png',
    status: '200',
    type: 'image',
    size: '1900KB',
    time: '19ms',
  },
  {
    name: 'file20.png',
    status: '200',
    type: 'image',
    size: '2000KB',
    time: '20ms',
  },
  {
    name: 'file21.png',
    status: '200',
    type: 'image',
    size: '2100KB',
    time: '21ms',
  },
  {
    name: 'file22.png',
    status: '200',
    type: 'image',
    size: '2200KB',
    time: '22ms',
  },
  {
    name: 'file23.png',
    status: '200',
    type: 'image',
    size: '2300KB',
    time: '23ms',
  },
  {
    name: 'file24.png',
    status: '200',
    type: 'image',
    size: '2400KB',
    time: '24ms',
  },
  {
    name: 'file25.png',
    status: '200',
    type: 'image',
    size: '2500KB',
    time: '25ms',
  },
  {
    name: 'file26.png',
    status: '200',
    type: 'image',
    size: '2600KB',
    time: '26ms',
  },
  {
    name: 'file27.png',
    status: '200',
    type: 'image',
    size: '2700KB',
    time: '27ms',
  },
  {
    name: 'file28.png',
    status: '200',
    type: 'image',
    size: '2800KB',
    time: '28ms',
  },
  {
    name: 'file29.png',
    status: '200',
    type: 'image',
    size: '2900KB',
    time: '29ms',
  },
  {
    name: 'file30.png',
    status: '200',
    type: 'image',
    size: '3000KB',
    time: '30ms',
  },
  {
    name: 'file31.png',
    status: '200',
    type: 'image',
    size: '3100KB',
    time: '31ms',
  },
  {
    name: 'file32.png',
    status: '200',
    type: 'image',
    size: '3200KB',
    time: '32ms',
  },
  {
    name: 'file33.png',
    status: '200',
    type: 'image',
    size: '3300KB',
    time: '33ms',
  },
  {
    name: 'file34.png',
    status: '200',
    type: 'image',
    size: '3400KB',
    time: '34ms',
  },
];
</script>

<template>
  <section class="table-container" :style="{ height: `${height}px` }">
    <ElTable
      v-if="height"
      :data="tableData"
      height="100%"
      class="neumorph-table"
      style="width: 100%;height: 100%;"
    >
      <ElTableColumn
        prop="name"
        label="NAME"
        min-width="30%"
        show-overflow-tooltip
      >
        <template #default="{ row }">
          <div class="cursor-pointer text-text_primary_blue! hover:text-text_primary_red!" @click="checkDetail(row)">
            {{ row.name }}
          </div>
        </template>
      </ElTableColumn>
      <ElTableColumn
        v-for="column in columns"
        :key="column.field"
        :prop="column.field"
        :label="column.label"
        :min-width="column.minWidth"
        show-overflow-tooltip
      />
      <ElTableColumn
        prop="operation"
        label="OPERATION"
        min-width="20%"
      >
        <template #default>
          <div class="flex items-center gap-2 h-10">
            <QuasiButton class="p-[2px]!">
              <IconCopyrightFilled :size="18" />
            </QuasiButton>
            <QuasiButton class="p-[2px]!">
              <IconLocationFilled :size="18" />
            </QuasiButton>
            <QuasiButton class="p-[2px]!">
              <IconLockFilled :size="18" />
            </QuasiButton>
          </div>
        </template>
      </ElTableColumn>
    </ElTable>
  </section>
</template>

<style scoped>
.table-container {
  border-radius: 10px;
  overflow: hidden;
  box-shadow:
    4px 4px 8px var(--btn_shadow_r),
    -4px -4px 8px var(--btn_shadow_l);
}
.neumorph-table {
  font-size: 12px;
  background: var(--container_bg);
  overflow: hidden;
}

:deep(.neumorph-table .el-table__inner-wrapper) {
  background: transparent;
}
:deep(.neumorph-table .el-table__header-wrapper),
:deep(.neumorph-table .el-table__body-wrapper) {
  background: transparent;
}

:deep(.neumorph-table .el-table__header .el-table__cell) {
  background: var(--btn_bg);
  border-right: 1px solid var(--gray_300);
  border-bottom: 1px solid var(--gray_300);
}

:deep(.neumorph-table .el-table__row .el-table__cell) {
  background: var(--btn_bg);
  border-bottom: 1px solid var(--gray_300);
}

:deep(.neumorph-table .el-table__row:hover .el-table__cell) {
  background: var(--table_hover_bg);
}
</style>
