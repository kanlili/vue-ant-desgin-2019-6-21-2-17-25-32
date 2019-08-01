<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div>
    <br/>
    姓名：<a-input placeholder="请输入姓名" class="name"/>
    性别：
    <a-radio-group name="radioGroup" :defaultValue="男">
    <a-radio :value="1">男</a-radio>
    <a-radio :value="2">女</a-radio>
    <a-button type="primary">Submit</a-button>
  </a-radio-group>
    
      <a-menu
    @click="handleClick"
    style="width: 256px"
    :defaultSelectedKeys="['1']"
    :openKeys.sync="openKeys"
    mode="inline"
  >
    <a-sub-menu key="sub1" @titleClick="titleClick">
      <span slot="title"><a-icon type="mail" /><span>Navigation One</span></span>
      <a-menu-item-group key="g1">
        <template slot="title"><a-icon type="qq" /><span>Item 1</span></template>
        <a-menu-item key="1">Option 1</a-menu-item>
        <a-menu-item key="2">Option 2</a-menu-item>
      </a-menu-item-group>
    </a-sub-menu>
  </a-menu>
  </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  // components: {
  //   HelloWorld
  // },
  data () {
    return {
      current: ['mail'],
      openKeys: ['sub1'],
    }
  },
  methods: {
    handleClick (e) {
      console.log('click', e)
    },
    titleClick (e) {
      console.log('titleClick', e)
    },
  },
  watch: {
    openKeys (val) {
      console.log('openKeys', val)
    },
  },

}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.name{
   width: 30px;
} */
</style>
