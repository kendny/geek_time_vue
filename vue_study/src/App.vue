<template>
    <div id="app">
        <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
        <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
        <input type="text" v-model="info">
        <button @click="handleClick">add</button>
        <TodoItem v-for="(item, key) in list" :item="item" v-bind:key="key">
          <!-- 
            插槽语法：
              vue2.6之前的语法： <template slot="slotname"></template>
              vue2.6之后的语法： <template v-slot:slotname></template>
           -->
            <template v-slot:item="itemProps">
              <span :style="{fontSize: '34px', color:itemProps.checked? 'red': 'blue'}">{{item}}--{{itemProps}}</span>
            </template>
        </TodoItem>
    </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import TodoItem from './components/TodoItem.vue'

export default {
    name: 'app',
    components: {
        TodoItem
    },
    data() {
        return {
            list: [],
            info: '',
            msg: "hello world"
        }
    },
    methods: {
        handleClick() {
            console.log(this.list)
            this.list.push(this.info)
            this.info = ''
        }
    }
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
} */
</style>
