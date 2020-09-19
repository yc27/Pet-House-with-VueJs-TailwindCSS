<template>
  <div class="flex justify-center px-2 py-8">
    <div class="bg-white shadow-md rounded border px-8 py-8 w-full max-w-sm">
      <h4 class="font-bold text-purple-800 text-3xl underline pb-2">{{ animal.name }} ({{ $route.params.type }})</h4>
      <p>
        <span class="text-gray-700 font-semibold"> Geneder: </span>
        <span class="text-gray-700 text-lg leading-relaxed capitalize"> {{ animal.gender }} </span> <br>

        <span class="text-gray-700 font-semibold"> Age: </span>
        <span class="text-gray-700 text-lg leading-relaxed capitalize"> {{ animal.age }} years </span> <br>

        <span class="text-gray-700 font-semibold"> Weight: </span>
        <span class="text-gray-700 text-lg leading-relaxed capitalize"> {{ animal.weight }} Kg</span> <br>

        <span class="text-gray-700 font-semibold"> Color: </span>
        <span class="text-gray-700 text-lg leading-relaxed capitalize"> {{ animal.color }} </span> <br>

        <span class="text-gray-700 font-semibold"> Notes: </span>
        <span class="text-gray-700 text-lg leading-relaxed capitalize"> {{ animal.notes }} </span> <br>

        <span class="text-gray-700 font-semibold"> Location: </span>
        <span class="text-gray-700 text-lg leading-relaxed capitalize"> {{ animal.location }} </span>
      </p>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'Pet',
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState(['cats', 'dogs'])
  },
  mounted () {
    const animal = this[this.$route.params.type][this.$route.params.id]
    this.animal = animal
  }
}
</script>
