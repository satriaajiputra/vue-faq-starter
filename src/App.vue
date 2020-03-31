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

export default {
  name: "App",
  components: {
    HeaderApp,
    Faq,
    FooterApp
  },
  data() {
    return {
      records: [
        {
          id: 1,
          title: "How do I cancle the order, I have placed?",
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores dolorum natus maiores error repellat, libero aliquam iure dolor aspernatur. Laborum est laboriosam totam. Error hic recusandae inventore, quas sequi dolorem!"
        },
        {
          id: 2,
          title: "How do I create a Return Request?",
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores dolorum natus maiores error repellat, libero aliquam iure dolor aspernatur. Laborum est laboriosam totam. Error hic recusandae inventore, quas sequi dolorem!"
        },
        {
          id: 3,
          title: "How do I cancle the order, I have placed?",
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores dolorum natus maiores error repellat, libero aliquam iure dolor aspernatur. Laborum est laboriosam totam. Error hic recusandae inventore, quas sequi dolorem!"
        }
      ]
    };
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

.container {
  max-width: 800px;
  margin: 0 auto;
}
</style>
