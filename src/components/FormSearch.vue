<template>
  <form class="form-search" :class="{ 'form-search_header': inHeader }">
    <input
      class="form-search__input"
      type="text"
      name="search"
      placeholder="Search question"
    />
  </form>
</template>

<script>
export default {
  props: {
    inHeader: {
      type: Boolean,
      default: false,
      required: false
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
