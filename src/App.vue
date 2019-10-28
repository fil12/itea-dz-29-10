<template>
    <div id="app">
        <Login></Login>
        <ToDos>
            <!-- слот не имеет доступа к области видимости копонента (wrap) -->
            <template v-slot:title>
                <h1>Todos</h1>
            </template>
            <template v-slot:input="slotProps">
                <h2>Введите ваше задание на день</h2>
                <div class="col-lg-8 col-lg-offset-2 ">
                    <div id="todo-list-example">
                        <form v-on:submit.prevent="addNewTodo">
                            <label for="new-todo">Добавить задачу</label>
                           <input-text
                                   v-model.lazy.trim="newTodoText"
                                   id="new-todo"
                                   placeholder="Добавить задачу"
                           />
                            <btn label="Добавить" type="submit"></btn>
                        </form>
                        <ol>
                            <li
                                    is="todo-item"
                                    v-for="(todo, index) in todos"
                                    v-bind:key="todo.id"
                                    v-bind:title="todo.title"
                                    v-on:remove="todos.splice(index, 1)"
                            ></li>
                        </ol>
                    </div>
                </div>
                <br>
                <span>{{ slotProps.add.email }}</span>
            </template>
        </ToDos>
    </div>
</template>

<script>

    import Login from './components/Login'
    import ToDos from "./components/ToDos"
    import InputText from "./components/inputs/InputText";
    import Btn from "./components/btns/Btn"
    import TodoItem from "./components/TodoItem";

    export default {
        name: 'app',
        components: {
            Login,
            ToDos,
            InputText,
            Btn,
            TodoItem
        },
        data() {
            return {
                newTodoText: '',
                todos: [],
                nextTodoId: 1,
            }
        },

        methods: {
            addNewTodo: function () {
                if (!this.newTodoText){
                    return;
                }
                this.todos.push({
                    id: this.nextTodoId++,
                    title: this.newTodoText
                })
                this.newTodoText = ''
            },
        }
    }
</script>

<style lang="scss">
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
