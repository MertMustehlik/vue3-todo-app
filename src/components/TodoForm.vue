<template>
    <div v-if="errors.length > 0" class="w-full  min-h-[50px] rounded-md bg-yellow-400 flex justify-start items-center p-5">
        <ul v-for="error in errors" class="list-disc ms-5">
            <li>{{error.message}}</li>
        </ul>
    </div>
    <div>
        <label for="first-name" class="block text-sm font-semibold leading-6 text-gray-900">Enter Todo</label>
        <div class="mt-1">
            <input v-model="form.name" class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6">
        </div>
        <div class="">
            <button @click="handleClick" class="px-5 py-2 bg-blue-900 hover:bg-blue-800 rounded mt-2 text-white w-full">Add</button>
        </div>
    </div>
</template>
<script>
export default {
    name: "TodoForm",
    emits: ["add-todo-item"],
    data(){
        return {
            form: {
                name: ""
            },
            errors: []
        }
    },
    methods:{
        handleClick(){
            this.errors = []
            if (this.form.name === ""){
                this.errors.push({"message": "Todo field is required"})
                return false;
            }
            this.$emit('add-todo-item', this.form)
            this.form.name = ""
        }
    }
}
</script>