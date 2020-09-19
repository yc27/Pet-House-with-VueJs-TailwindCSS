<template>
  <nav class="flex flex-wrap justify-center bg-teal-500 p-6 m-0">
    <div class="flex w-full items-center justify-center text-blue-900 mb-2">
      <svg
        class="fill-current h-8 w-8 mr-2"
        width="54"
        height="54"
        viewBox="0 0 54 54"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M13.5 22.1c1.8-7.2 6.3-10.8 13.5-10.8 10.8 0 12.15 8.1 17.55 9.45 3.6.9 6.75-.45 9.45-4.05-1.8 7.2-6.3 10.8-13.5 10.8-10.8 0-12.15-8.1-17.55-9.45-3.6-.9-6.75.45-9.45 4.05zM0 38.3c1.8-7.2 6.3-10.8 13.5-10.8 10.8 0 12.15 8.1 17.55 9.45 3.6.9 6.75-.45 9.45-4.05-1.8 7.2-6.3 10.8-13.5 10.8-10.8 0-12.15-8.1-17.55-9.45-3.6-.9-6.75.45-9.45 4.05z"
        />
      </svg>
      <span class="font-semibold text-2xl tracking-tight">Pet House</span>
    </div>

    <div class="flex w-full items-center justify-center">
      <router-link to="/" class="text-indigo-600 hover:font-semibold">Home</router-link>
      <span class="px-2 text-gray-700">|</span>
      <router-link to="/cats" class="text-indigo-600 hover:font-semibold">Cats</router-link>
      <span class="px-2 text-gray-700">|</span>
      <router-link to="/dogs" class="text-indigo-600 hover:font-semibold">Dogs</router-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Nav'
}
</script>

<style scoped>
nav {
  margin: 0 !important;
}
</style>
