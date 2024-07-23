<template>
    <div>
        <li class="px-5 py-2 ring-1 ring-gray-800 rounded flex justify-between items-center my-2">
            <span>#{{ item?.id }} | {{ item?.name }}</span>
            <button @click="removeTodo(item)" class="px-3 py-1 bg-red-600 text-white rounded-md text-sm">Delete</button>
        </li>
    </div>
</template>
<script>
export default {
    name: "TodoListItem",
    props: ["item"],
    inject: ["removeTodo"]
}
</script>