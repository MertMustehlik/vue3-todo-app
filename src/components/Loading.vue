<template>
   <div v-if="isLoading" class="flex justify-center items-center">
       <i class="fa-solid fa-spinner animate-spin"></i>
   </div>
</template>
<script>
export default {
    name: "Loading",
    props: {
        isLoading: {
            type: Boolean
        }
    }
}
</script>