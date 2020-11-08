<template>
  <ul>
    <li
      :class="{ active: modelValue === 'poor' }"
      @click="activateButton('poor')">
      <button type="button">Poor</button>
    </li>
    <li
      :class="{ active: modelValue === 'average' }"
      @click="activateButton('average')">
      <button type="button">Average</button>
    </li>
    <li
      :class="{ active: modelValue === 'good' }"
      @click="activateButton('good')">
      <button type="button">Good</button>
    </li>
  </ul>
</template>

<script>
export default {
  name: "RatingControl",
  props: ['modelValue'],
  emits: ['update:modelValue'],
  methods: {
    activateButton(name) {
      this.activeButton = name;
      this.$emit('update:modelValue', name);
    }
  }
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0.5rem 0;
  padding: 0;
  display: flex;
}

li {
  margin: 0 1rem;
  border: 1px solid #ccc;
  padding: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

button {
  font: inherit;
  border: none;
  background-color: transparent;
  cursor: pointer;
}

.active {
  border-color: #0076bb;
}

.active button {
  color: #0076bb;
}
</style>