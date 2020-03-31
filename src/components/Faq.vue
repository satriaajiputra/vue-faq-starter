<template>
  <div class="faq">
    <faq-item
      v-for="(faq, i) in records"
      :key="i"
      :item="faq"
      @collapse="collapseItem($event, i)"
    />
  </div>
</template>

<script>
import Vue from "vue";
import FaqItem from "@/components/FaqItem.vue";

export default {
  props: {
    records: {
      type: Array,
      required: false,
      default: () => []
    }
  },
  components: {
    FaqItem
  },
  methods: {
    collapseItem(state, i) {
      for (let r in this.records) {
        Vue.set(this.records[r], "active", false);
      }

      Vue.set(this.records[i], "active", state);
    }
  }
};
</script>

<style lang="scss" scoped></style>
