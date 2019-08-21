<template>
    <div class="Info">
        hello info component
        <button type="button" @click="add()">添加</button>
    </div>
</template>

<script>
import store from '@/store'

export default {
    name:'Info',
    store,
    methods:{
        add(){
           // console.log('123');
            store.commit('increase')
        }
    }
}
</script>