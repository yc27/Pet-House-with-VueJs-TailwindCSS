<template>
  <div class="container text-center py-4 mx-auto">
    <p class="text-2xl text-center font-bold text-blue-900 py-4">Adopt Your New Best Friend.</p>
    <button
      @click="toggleForm"
      class="bg-green-600 hover:bg-green-700 text-gray-100 rounded focus:outline-none focus:shadow-outline px-4 py-2"
    >Add New Pet</button>

    <div v-if="showForm" class="w-full max-w-xs mx-auto mt-8">
      <form
        @submit.prevent="handleSubmit"
        class="bg-white shadow-md border rounded text-left px-8 py-6 mb-4"
      >
        <div class="mb-4">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="pet-name">Pet's Name</label>
          <input
            v-model="formData.name"
            class="w-full shadow appearance-none border rounded py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="pet-name"
            type="text"
            placeholder="Pet Name"
          />
        </div>

        <div class="mb-4">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="pet-type">Pet Type</label>
          <div class="relative">
            <select
              v-model="formData.type"
              class="block w-full shadow appearance-none border rounded bg-gray-200 text-gray-700 py-2 px-3 pr-8 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
              id="pet-type"
            >
              <option>cats</option>
              <option>dogs</option>
            </select>
            <div
              class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700"
            >
              <svg
                class="fill-current h-4 w-4"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
              >
                <path
                  d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                />
              </svg>
            </div>
          </div>
        </div>

        <div class="mb-6">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="pet-age">Age</label>
          <input
            v-model="formData.age"
            class="w-full shadow appearance-none border rounded py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            id="pet-age"
            type="number"
            placeholder="0"
          />
        </div>

        <div class="flex items-center justify-end">
          <button
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline mr-2"
            type="submit"
          >Save</button>

          <button
            @click="toggleForm"
            class="bg-red-500 hover:bg-red-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
            type="button"
          >Cancel</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  name: 'Home',
  data () {
    return {
      showForm: false,
      formData: {
        name: '',
        age: 0,
        type: null
      }
    }
  },
  methods: {
    ...mapActions(['addPet']),
    toggleForm () {
      this.showForm = !this.showForm
    },
    handleSubmit () {
      const { name, age, type } = this.formData
      const payload = {
        type,
        pet: {
          name,
          age
        }
      }
      this.addPet(payload)
      this.toggleForm()
      this.formData = {
        name: '',
        age: 0,
        type: null
      }
    }
  }
}
</script>
