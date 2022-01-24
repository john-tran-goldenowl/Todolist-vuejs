<template>
    <div class="item" :class="{'done' : content.done, 'pending': !content.done}">
            <div class="absolue">
                <i v-if="content.done"  class="fas fa-times-circle" @click="Check"></i>
                <i v-else class="fas fa-check-circle" @click="Check"></i>
                <i  class="fas fa-trash" @click="Delete"></i>
            </div>
            <h3>{{content.task}}</h3>
            <p v-if="content.done">done</p>
            <p v-else>pending</p>
        </div>
</template>
<script>
export default {
    name : 'itemTodolist',
    props:  {
        content : Object    
    },
    methods: {
        Check(){
            this.$emit('updateCheck')
        },
        Delete(){
            this.$emit('updateDelete')
        }
    }
   
}
</script>