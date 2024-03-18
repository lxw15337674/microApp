<script setup
        lang="ts">
        import { ref, watchEffect, watch } from "vue";
        import useSelections from "../index";
        const data = ref([
          {
            id: 1,
            name: "John",
          },
          {
            id: 2,
            name: "Doe",
          },
          {
            id: 3,
            name: "Smith",
          },
        ]);
        const checked = ref([])
        const {
          allSelected,
          select,
          isSelected,
          partiallySelected
        } = useSelections(data, checked, "name");
</script>

<template>
  <div>
    {{ checked }}
    <div>
      <el-checkbox v-model="allSelected"
                   :indeterminate="partiallySelected"
                   label="全选" />
      <div>
        <el-checkbox v-for="item in data"
                     :key="item.id"
                     :model-value="isSelected(item)"
                     @change="v=>select(item,v as boolean)"
                     :label="item.name">
        </el-checkbox>
      </div>

    </div>
  </div>
</template>
