<template>
  <div id="app">
    <header-app />
    <div class="container">
      <faq :records="records" />
    </div>
    <footer-app />
  </div>
</template>

<script>
import HeaderApp from "@/components/HeaderApp.vue";
import FooterApp from "@/components/FooterApp.vue";
import Faq from "@/components/Faq.vue";
import eventBus from "@/utils/event-bus";

export default {
  name: "App",
  components: {
    HeaderApp,
    Faq,
    FooterApp
  },
  data() {
    return {
      recordsData: [],
      records: []
    };
  },
  created() {
    fetch(
      "https://my-json-server.typicode.com/satriaajiputra/vue-faq-starter/faq"
    )
      .then(res => res.json())
      .then(json => {
        this.recordsData = json;
        this.records = json;
      });
  },
  mounted() {
    eventBus.$on("search", q => this.search(q));
  },
  methods: {
    search(q) {
      if (q.length < 1) {
        this.records = this.recordsData;
      } else {
        this.records = this.recordsData.filter(
          row =>
            row.title.toLowerCase().match(q) ||
            row.content.toLowerCase().match(q)
        );
      }
    }
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=PT+Serif:400,700&display=swap");
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "PT Serif", serif;
}

body {
  color: #777;
}

.container {
  max-width: 800px;
  margin: 0 auto;
}
</style>
