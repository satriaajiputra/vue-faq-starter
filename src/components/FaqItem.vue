<template>
  <div class="faq-item">
    <button class="faq-item__btn-collapse" @click.prevent="collapse">
      <span v-if="!item.active">&plus;</span>
      <span v-else>&minus;</span>
    </button>
    <div class="faq-item__wrapper">
      <div class="faq-item__heading" @click.prevent="collapse">
        <h3>{{ item.title }}</h3>
      </div>
      <div v-show="item.active || false" class="faq-item__content">
        <p>
          {{ item.content }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FaqItem",
  props: {
    item: {
      type: Object,
      required: true
    }
  },
  methods: {
    collapse() {
      this.$emit("collapse", !(this.item.active || false));
    }
  }
};
</script>

<style lang="scss" scoped>
.faq-item {
  border-bottom: 1px solid #ebebeb;
  padding: 1.5rem 0;
  display: flex;
  align-items: flex-start;
  &:last-child {
    border-bottom: none;
  }
}
.faq-item__btn-collapse {
  background: #1dcc57;
  color: #fff;
  border: none;
  outline: none;
  width: 1.5rem;
  height: 1.5rem;
  border-radius: 100%;
  cursor: pointer;
  font-weight: bold;
}
.faq-item__wrapper {
  flex: 1;
  margin-left: 1rem;
}
.faq-item__content {
  margin-top: 1rem;
  color: #777;
  line-height: 1.7;
  overflow: hidden;
  transition: all 0.3s ease-in-out;
}
.faq-item__heading {
  cursor: pointer;
  user-select: none;
  color: #333;
}
</style>
