<template>
  <div class="mt-4">
    <el-input
      v-model="input"
      placeholder="Please input"
      class="input-with-select"
    >
      <template #prepend>
        <el-select
          v-model="select"
          placeholder="Select"
          style="width: 115px"
          clearable
        >
          <el-option label="包含" value="包含" />
          <el-option label="不包含" value="不包含" />
        </el-select>
      </template>
      <template #append>
        <el-button :icon="Search" />
      </template>
    </el-input>
  </div>
</template>

<script setup lang="ts">
import { ref, defineProps, defineEmits, computed } from 'vue';
import { Search } from '@element-plus/icons-vue';

const props = defineProps({
  modelValue: Array,
});
const emit = defineEmits(['update:modelValue']);

const select = computed({
  get: () => props.modelValue?.[0],
  set: (newSelect) => emit('update:modelValue', [newSelect, input.value]),
});

const input = computed({
  get: () => props.modelValue?.[1],
  set: (newInput) => emit('update:modelValue', [select.value, newInput]),
});
</script>

<style>
.input-with-select .el-input-group__prepend {
  background-color: var(--el-fill-color-blank);
}
</style>
