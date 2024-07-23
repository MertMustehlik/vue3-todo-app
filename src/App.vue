<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header class="w-100 bg-gray-300 flex justify-center items-center">
      <nav class="flex justify-center items-center gap-3">
          <RouterLink to="/" class="flex items-center gap-2 p-[10px] rounded-md bg-gray-100 hover:text-blue-600"
                      active-class="text-blue-600">
              <div class="flex flex-center w-[20px]">
                  <i class="fa fa-house"></i>
              </div>
              <span class="text-sm font-semibold">Dashboard</span>
          </RouterLink>
          <RouterLink to="/todo" class="flex items-center gap-2 p-[10px] rounded-md  bg-gray-100 hover:text-blue-600"
                      active-class="text-blue-600">
              <div class="flex flex-center w-[20px]">
                  <i class="fa fa-list"></i>
              </div>
              <span class="text-sm font-semibold">Todo</span>
          </RouterLink>
      </nav>
  </header>
  <main class="py-16 bg-gray-100">
      <RouterView />
  </main>
</template>

<style scoped>
main {
    min-height: calc(100vh - var(--header-height));
}

header{
    height: var(--header-height);
}
</style>
