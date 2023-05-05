<!-- components/SimpleTable.vue -->
<template>
  <el-table
    :data="data"
    style="width: 100%"
  >
    <template v-for="column in props.columns" :key="column">
      <RenderTableColumn v-bind="column" />
    </template>
  </el-table>
</template>

<script lang="tsx" setup name="SimpleTable">

const props = defineProps({
  data: Array<any>,
  columns: Array<any>
})

const RenderTableColumn = (column: any) => {
  return (
    <el-table-column>
      {{
        default: (scope: any) => {
          if (column.render) return column.render(scope)
          return column.prop
        },
        header: () => {
          if (column.headerRender) return column.headerRender(column)
          return column.label
        }
      }}
    </el-table-column>
  )
}

</script>