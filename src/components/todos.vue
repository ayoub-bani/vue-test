<template>
  <div class="container">
    <div class="bg-white">
      <!-- Card -->
      <div class="card border-0 mt-3 bg-primary d-flex justify-content-center">
        <div class="container hover d-flex align-items-center">
          <span class="font-weight-bold mr-auto">{{ name }}</span>
          <a @click="$emit('deleteTodos')" class="bg-white rounded p-1" href="#"
            ><img
              class="custom-image-size"
              src="@/assets/images/wrong.png"
              alt="delete this todo icon"
          /></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'todos',
  components: {},
  emits: ['deleteTodos'],
  props: {
    name: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      list: [],
    }
  },

  methods: {
    add() {},
    complete() {},
  },
}
</script>

<style></style>
