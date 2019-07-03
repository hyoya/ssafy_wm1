<style>
cFooter {
  margin-top: 619px;
}
.writer__wrap {
  margin: auto;
  margin-top: 90px;
  width: 90%;
  height: 520px;
}
.writer__title__content {
  background-color: aqua;
  width: 44%;
  height: 30px;
}
.writer__title__name {
  background-color: yellow;
  width: 5%;
  height: 30px;
}
.writer__title {
  display: flex;
  align-content: flex-start;
}
html,
body,
#editor {
  margin: 0;
  height: 40vw;
  font-family: "Helvetica Neue", Arial, sans-serif;
  color: #333;
}

textarea,
#editor div {
  display: inline-block;
  width: 49%;
  height: 100%;
  vertical-align: top;
  box-sizing: border-box;
  padding: 0 20px;
}

textarea {
  border: none;
  border-right: 1px solid #ccc;
  resize: none;
  outline: none;
  background-color: #f6f6f6;
  font-size: 14px;
  font-family: "Monaco", courier, monospace;
  padding: 20px;
}

code {
  color: #f66;
}

#titleDiv{
        margin: 2vw 0;
}


#titletag{
  margin-left: 4vw;
  font-size: 2vw;
}

#title{
  margin-left:2vw;
  font-size : 2vw;
  width: 81vw;
}

</style>

<!-- *********************** -->


<template>
  <v-layout mt-5 wrap>
    <v-flex>
      <h1>포트폴리오를 작성합시다!</h1>

      <div id="titleDiv">
        <span id="titletag">제목</span>
        <input type="text" id="title" />
      </div>

      <div id="editor">
        <textarea :value="input" @input="update"></textarea>
        <div v-html="compiledMarkdown"></div>
      </div>

    </v-flex>
  </v-layout>
</template>

<!-- *********************** -->


<script>
export default {
  name: "PFEditor",
  data() {
    return {
      input: "# Please write here."
    };
  },
  computed: {
    compiledMarkdown: function() {
      return marked(this.input, { sanitize: true });
    }
  },
  methods: {
    update: _.debounce(function(e) {
      this.input = e.target.value;
    }, 100)
  }
};
</script>
