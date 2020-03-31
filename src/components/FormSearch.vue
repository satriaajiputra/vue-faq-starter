<template>
  <form class="form-search" :class="{ 'form-search_header': inHeader }">
    <input
      class="form-search__input"
      type="text"
      name="search"
      placeholder="Search question"
      v-model="query"
    />
  </form>
</template>

<script>
import eventBus from "@/utils/event-bus";

export default {
  props: {
    inHeader: {
      type: Boolean,
      default: false,
      required: false
    }
  },
  data() {
    return {
      query: ""
    };
  },
  watch: {
    query(n) {
      eventBus.$emit("search", n);
    }
  }
};
</script>

<style lang="scss" scoped>
.form-search_header {
  margin-top: 2rem;
}
.form-search__input {
  width: 100%;
  background-color: transparent;
  border: none;
  outline: none;
  display: block;
  border-radius: 5px;
  background-color: #fff;
  padding: 1rem;
  font-size: 1rem;
}
</style>
