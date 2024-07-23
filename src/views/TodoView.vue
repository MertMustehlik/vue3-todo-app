<template>

    <div class="flex justify-center items-center">
        <div class="bg-white rounded-md shadow w-[500px]">
            <div class="border-b border-gray-900">
                <h3 class="text-2xl font-semibold text-center py-5">Todo List</h3>
            </div>
            <div class="flex flex-col gap-7 px-7 my-9">
                <TodoForm @add-todo-item="addTodo"/>
                <TodoList :todos="todos"/>
            </div>
        </div>
    </div>
</template>
<script>
import TodoList from "@/components/TodoList.vue";
import TodoForm from "@/components/TodoForm.vue";

export default {
    name: "TodoView",
    components: {TodoForm, TodoList},
    data(){
        return {
            todos: false
        }
    },
    created() {
        setTimeout(() => {
            this.todos = []
        }, 1900)
    },
    provide() {
      return {
          "removeTodo": this.removeTodo
      }
    },
    methods: {
        addTodo(event){
            this.todos.push({id: new Date().getTime(), name: event.name})
        },
        removeTodo(event){
            this.todos = this.todos.filter((item) => item.id !== event.id)
        }
    }
}
</script>