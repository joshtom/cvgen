<template>
  <section class="flex pb-2 mt-5 border-separate">
    <div class="w-2/4 mr-3">
      <h1 class="text-1xl font-serif mb-0 pb-0 text-gray-600 font-bold uppercase mb-3">About Me</h1>
      <h3 class="text-1xl text-gray-600 mb-3 pt-0">{{ info.summary }}</h3>
    </div>

    <div class="w-1/4 object-right tracking-wider">
      <h1 class="text-1xl font-serif mb-0 pb-0 text-gray-600 font-bold uppercase mb-3">Contact</h1>

      <h3 class="text-sm text-gray-600">
        <fa :icon="['fas', 'phone']" class="mr-1" />
        {{ info.phone }}
      </h3>
      <h3 class="text-sm text-gray-600 pt-3">
        <fa :icon="['fas', 'envelope']" class="mr-1" />
        {{ info.email }}
      </h3>

      <h3 class="text-sm text-gray-600 pt-3">
        <fa :icon="['fas', 'home']" class="mr-1" />
        {{ info.website }}
      </h3>
    </div>
  </section>
</template>

<script>
import { mapGetters, mapActions } from "vuex";

export default {
  computed: mapGetters({ info: "basicinfo/getData" }),
  methods: {
    ...mapActions({ loadData: "basicinfo/loadData" })
  },
  created() {
    this.loadData();
  }
};
</script>

<style scoped>
h3 {
  margin-top: -10px;
}
</style>