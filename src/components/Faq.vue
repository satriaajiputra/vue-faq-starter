<template>
  <div class="faq">
    <faq-item
      v-for="(faq, i) in records"
      :key="i"
      :item="faq"
      @collapse="collapseItem($event, i)"
    />
    <p class="empty-data" v-if="records.length < 1">
      No frequently asked quesstions founds.
    </p>
  </div>
</template>

<script>
import Vue from "vue";
import FaqItem from "@/components/FaqItem.vue";

export default {
  props: {
    records: {
      type: Array,
      required: true
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

<style lang="scss" scoped>
.empty-data {
  text-align: center;
  border-bottom: 1px solid #f2f2f2;
  padding-bottom: 2rem;
}
</style>
