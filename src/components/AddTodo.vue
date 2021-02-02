<template>
<div>
    <form @submit="addTodo">
        <input type="text" v-model="title" name="title " placeholder="List of ToDos to do...." >
        <input type="submit" value="submit" class="submitButton" >
    </form>
</div>
</template>
<script>
// import uuid from 'uuid/dist/v4';
export default {
    name: "AddTodo",
    data(){
        return{ title:''}
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
            //    id: uuid(),
                title: this.title,
                completed:false
            }
            // the above constructed the data we wanted, and now we need 
            // to send this to the parent class using emit
            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>
<style scoped>
    form { display: flex;}
    input[type="text"]{
        flex : 10;
        padding: 5px;
    }
    input[type="submit"]{
        flex : 2; 
    }
</style>