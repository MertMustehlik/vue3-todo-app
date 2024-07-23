<template>
    <div>
        <Loading class="h-[150px]" :isLoading="!todos"/>
        <div v-if="todos.length <= 0" class="flex justify-center items-center font-semibold text-sm text-gray-600 py-6">
            No Data
        </div>
        <ul v-for="todo in todos">
            <TodoListItem :item="todo"/>
        </ul>
    </div>
</template>
<script>
import TodoListItem from "@/components/TodoListItem.vue";
import Loading from "@/components/Loading.vue";

export default {
    name: "TodoList",
    components: {Loading, TodoListItem},
    props: ["todos"]
}
</script>