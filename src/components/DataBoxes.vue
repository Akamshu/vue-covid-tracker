<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box 1 -->
    <div class="shadow-md bg-orange-100 p-10 text-center rounded">
      <h3 class="text-3xl text-pink-700 font-bold mb-4"><i class="fa fa-bed"></i></h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>

    <!-- Box 2 -->
    <div class="shadow-md bg-green-300 p-10 text-center rounded">
      <h3 class="text-3xl text-green-700 font-bold mb-4"><i class="fa fa-running"></i></h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">Recovered:</span>
        {{ numberWithCommas(stats.NewRecovered) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalRecovered) }}
      </div>
    </div>


    <!-- Box 3 -->
    <div class="shadow-md bg-red-400 p-10 text-center rounded">
      <h3 class="text-3xl text-red-600 font-bold mb-4"><i class="fa fa-cross"></i></h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ numberWithCommas(stats.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DataBoxes',
  props: ['stats'],
  methods: {
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
    },
  },
}
</script>
