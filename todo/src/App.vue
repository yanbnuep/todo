<template>
    <div id="app">
        <section class="header">
            <h1>Todo List</h1>
            <input type="text" class="newTask-ipt" placeholder="Add a plane" autofocus autocomplete="off" v-model="newTodo" @keyup.enter="addTodo" @click="activeDetail" @blur="inActiveDetail">
            <div class="detail" v-show="editingDetail">
                <label for="addDetail"></label>
                <textarea name="" id="addDetail" cols="30" rows="10"></textarea></div>
        </section>
        <section class="main">
            <ul class="todoList">
                <li class="todo" v-for="todo in todos"></li>
            </ul>
        </section>
    </div>
</template>
<script>
    export default{
        name: 'app',
        data(){
            return {
                newTodo: '',
                editingDetail: false
            }
        },
        computed: {},
        methods: {
            activeDetail: function () {
                this.editingDetail = true;
            },
            inActiveDetail: function () {
                this.editingDetail = false;
            }
        }
    }
</script>