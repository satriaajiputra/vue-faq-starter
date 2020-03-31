<template>
  <header class="header">
    <div class="container">
      <h1 class="header__title">
        Frequently Asked Questions
      </h1>
      <form-search :in-header="true" />
    </div>
  </header>
</template>

<script>
import FormSearch from "@/components/FormSearch.vue";

export default {
  components: {
    FormSearch
  }
};
</script>

<style lang="scss" scoped>
.header {
  background-color: #1dcc57;
  padding: 2rem;
  margin-bottom: 2rem;
}
.header__title {
  color: #fff;
  text-align: center;
}
</style>
