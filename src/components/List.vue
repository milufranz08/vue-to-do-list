<template>
  <ul class="list_wrapper">
    <li
      class="list_item"
      v-for="(data, index) in list"
      :key="index"
      @click="onClick(index)"
    >
      {{ data }}
    </li>
  </ul>
</template>

<script>
export default {
  name: "List",
  props: {
    list: Array
  },
  methods: {
    onClick(index) {
      this.$emit("clicked", index);
    }
  }
};
</script>

<style>
.list_wrapper {
  list-style-type: none;
  margin: auto;
  padding: 1em;
  width: 50%;
}

.list_item {
  color: white;
  margin: 0.5em;
  padding: 1em;
  background-color: #ff04bd;
}

.list_item:hover {
  font-weight: bold;
  background-color: #b9168e;
}
</style>
