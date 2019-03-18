<template>
    <div>
            <h3>Add Todo</h3>
            <div class="add">
                <form @submit="onSubmit">
                    <input type="text" name="" v-model="title" placeholder="Add Todo..." id="">
                    <input type="submit" value="Submit"/>
                </form>
            </div>
    </div>
</template>

<script>
import { mapActions } from 'vuex';
export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        ...mapActions(['addTodo']),
        onSubmit(e) {
            e.preventDefault();
            this.addTodo(this.title);
        }
    }
}
</script>

<style>
 form {
     display: flex;
 }
 input[type="text"] {
     flex: 10;
     padding: 10px;
     border: 1px solid #41b883 solid;
     cursor: pointer;
 }
 input[type="submit"] {
     flex: 2;
     background:#41b883;
     color:#fff;
     border:1px solid #41b883 solid;
     cursor: pointer;
 }

</style>
