
<template>
<div class="demo1">
    <ul>
        <li v-for="(item,index) in lists" @click="choose(index)" :class="{active:index == current && current !== ''}" :key="index">{{item}}</li>
    </ul>
    <button type="button" @click="add()">添加</button>
    <ul>
        <li v-for="(item,index) in target" :key="index">{{item}}</li>
    </ul>
</div>

</template>

<script>


export default {
    name:'demo1',
    data () {
    //这里存放数据
    return {
        current:'',
        lists:[1,2,3,4,5,6,7,8,9],
        target:[]
    };
},
//监听属性 类似于data概念
computed: {},
//监控data中的数据变化
watch: {},
//方法集合
methods: {
    choose (index) {
        this.current = index;
        console.log(index)
    },
    add () {
        if(this.current === ''){return}
        this.target.push(this.lists[this.current]);
        this.current = '';
    }
},
//生命周期 - 创建完成（可以访问当前this实例）
created() {

},
//生命周期 - 挂载完成（可以访问DOM元素）
mounted() {

},
beforeCreate() {}, //生命周期 - 创建之前
beforeMount() {}, //生命周期 - 挂载之前
beforeUpdate() {}, //生命周期 - 更新之前
updated() {}, //生命周期 - 更新之后
beforeDestroy() {}, //生命周期 - 销毁之前
destroyed() {}, //生命周期 - 销毁完成
activated() {}, //如果页面有keep-alive缓存功能，这个函数会触发
}
</script>
<style lang='scss' scoped>
    li.active{
        background: gray;
    }

</style>