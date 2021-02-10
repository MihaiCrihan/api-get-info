<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome Cronix',
      articles: 'loading'
    }
  },
  created () {
    this.search()
  },
  methods: {
    search: function () {
      fetch(`https://merax.herokuapp.com/todo_list`)
        .then(response => response.json())
        .then(json => {
          this.articles = json
        })
    }
  }
}
</script>

<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div id="divContent">
      {{ articles }}
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .SearchInput {
    width: 100%;
    padding: 1.5em 1em;
    font-size: 1em;
    outline: 0;
    border: 5px solid #41B883;
  }
  .Results {
    margin: 0;
    padding: 0;
    text-align: left;
    position: relative;
  }
  .Results li {
    background: rgba(53, 73, 94, 0.3);
    margin: 0;
    padding: 1em;
    list-style: none;
    width: 100%;
    border-bottom: 1px solid #394E62;
    transition: ease-in-out 0.5s;
  }
  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.3s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
</style>
