<template>
    <!-- <li class="item">{÷{item}}</li> -->

    <!-- 插槽 -->
    <li class="item">
        <!-- 作用域插槽的使用场景：将子组件的值或状态通过作用域插槽传递到父组件，进而控制相关的的 -->
        <input type="checkbox" v-model="checked">
        <slot name="item" v-bind="{checked}"></slot>
    </li>
</template>

<script>
export default {
    name: "TodoItem",
    props: {
        item: String,
    },
    data(){
        return {
            checked: false
        }
    }
}
</script>


<style scoped>
/*scoped: 将全局样式改变为局部样式*/ 
.item {
    color: rebeccapurple;
}
</style>


