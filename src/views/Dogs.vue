<template>
  <div>
    <h2 class="text-center text-blue-900 font-bold text-3xl my-4">Dogs</h2>

    <div class="flex justify-center px-4">
      <table class="table-auto shadow-md">
        <thead>
          <tr class="bg-indigo-500 text-gray-100">
            <th class="px-4 py-2 border border-gray-400">Name</th>
            <th class="px-4 py-2 border border-gray-400">Breed</th>
            <th class="px-4 py-2 border border-gray-400">Gender</th>
            <th class="px-4 py-2 border border-gray-400">Age</th>
            <th class="px-4 py-2 border border-gray-400">Color</th>
            <th class="px-4 py-2 border border-gray-400">Weight</th>
            <th class="px-4 py-2 border border-gray-400">Location</th>
            <th class="px-4 py-2 border border-gray-400">Nots</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(dog, index) in dogs"
            :key="index"
            class="bg-white hover:bg-indigo-200 hover:text-gray-900"
          >
            <td class="border px-4 py-2 underline text-blue-800">
              <router-link :to="{ name: 'pet', params:{type:'dogs', id: index}}">{{ dog.name }}</router-link>
            </td>
            <td class="border px-4 py-2">{{ dog.breed }}</td>
            <td class="border px-4 py-2">{{ dog.gender }}</td>
            <td class="border px-4 py-2">{{ dog.age }}</td>
            <td class="border px-4 py-2">{{ dog.color }}</td>
            <td class="border px-4 py-2">{{ dog.weight }}</td>
            <td class="border px-4 py-2">{{ dog.location }}</td>
            <td class="border px-4 py-2">{{ dog.notes }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'Dogs',
  computed: {
    ...mapState(['dogs'])
  }
}
</script>
