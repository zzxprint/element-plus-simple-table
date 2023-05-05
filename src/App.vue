<!-- App.vue -->
<template>
  <SimpleTable :columns="columns" :data="tableData" />
</template>

<script setup lang="tsx">
import SimpleTable from './components/SimpleTable.vue'

const columns = [
  {
    label: 'Date',
    prop: 'date',
    render: (scope: any) => {
      return (
        <div style="display: flex; align-items: center">
          <el-icon><timer /></el-icon>
          <span style="margin-left: 10px">{ scope.row.date }</span>
        </div>
      )
    }
  },
  {
    label: 'Name',
    prop: 'name',
    render: (scope: any) => {
      return (
        <el-tag>{ scope.row.name }</el-tag>
      )
    }
  },
  {
    label: 'Add.',
    prop: 'address'
  },
  {
    label: 'Operations',
    prop: '',
    render: () => {
      return (
        <div>
          <el-button size="small">Edit</el-button>
          <el-button size="small" type="danger">Delete</el-button>
        </div>
      )
    }
  },
]

const tableData = [
  {
    date: '2016-05-03',
    name: 'Tom',
    address: 'No. 189, Grove St, Los Angeles',
  }
]
</script>