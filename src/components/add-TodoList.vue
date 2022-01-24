<template>
      <div class="text-box">
            <input v-model="task" type="text"  id="task" placeholder="TASK">
            <button id="addtolist" @click="addToList">ADD</button>
        </div>
</template>
<script>
export default {
    name: 'addTodolist',
    props: {
        items:Object
    },
    data(){
        return{
            item :[],
            task:null, 
            id:null,
            done:false 
        }
    },
    methods:{
        addToList(){
            this.id = this.items[this.items.length-1]._id + 1;
            this.item= {
                '_id' : this.id,
                'task' : this.task,
                'done' : this.done
            }
            this.$emit('addtoToDoList',this.item)
            this.task = "";
        }

    }
}

</script>