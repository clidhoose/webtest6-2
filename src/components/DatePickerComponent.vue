<template>
    <el-radio-group v-model="size" aria-label="size control">
      <el-radio-button value="large">large</el-radio-button>
      <el-radio-button value="default">default</el-radio-button>
      <el-radio-button value="small">small</el-radio-button>
    </el-radio-group>
    <div class="demo-date-picker">
      <div class="block">
        <span class="demonstration">Default</span>
        <el-date-picker
          v-model="value1"
          type="date"
          placeholder="Pick a day"
          :size="size"
        />
      </div>
      <div class="block">
        <span class="demonstration">Picker with quick options</span>
        <el-date-picker
          v-model="value2"
          type="date"
          placeholder="Pick a day"
          :disabled-date="disabledDate"
          :shortcuts="shortcuts"
          :size="size"
        />
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        size: 'default',
        value1: null,
        value2: null,
        disabledDate(time) {
          return time.getTime() < Date.now() - 8.64e7;
        },
        shortcuts: [
          {
            text: 'Today',
            onClick(picker) {
              picker.$emit('pick', new Date());
            },
          },
          {
            text: 'Yesterday',
            onClick(picker) {
              const date = new Date();
              date.setTime(date.getTime() - 3600 * 1000 * 24);
              picker.$emit('pick', date);
            },
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .demo-date-picker .block {
    margin: 20px 0;
  }
  .demo-date-picker .demonstration {
    display: inline-block;
    width: 150px;
    font-size: 14px;
    color: #8492a6;
  }
  </style>