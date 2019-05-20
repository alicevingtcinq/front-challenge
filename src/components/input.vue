<template>
  <div>
    <label :for="name" v-if="label">{{label}}</label>
    <input
    class="input"
    v-model="sync_model"
    :name="name"
    :id="name">
    <p>Choice : {{ sync_model }}</p>
  </div>
</template>

<script>

export default {
  name: 'vqInput',
  props: {
    label: String,
    model: String,
    name: String,
  },
  computed: {
    sync_model: {
      get() {
        return this.model
      },
      set(val) {
        this.$emit('update:model', val)
      }
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
