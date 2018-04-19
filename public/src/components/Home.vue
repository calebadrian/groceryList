<template>
  <div class="home">
    <h1>Build a Grocery List!</h1>
    <h5>Copy and paste the ingredients from a recipe into the text box below and we will help you generate a grocery list!</h5>
    <form @submit.prevent="addToList">
      <textarea rows="5" cols="50" placeholder="Paste your text here" v-model="ingredients"></textarea>
      <button type="submit" class="btn btn-success">Submit</button>
    </form>
    <div>
      <h3>Meat</h3>
      <h3>Produce</h3>
      <h3>Canned Goods</h3>
      <h3>Other</h3>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Home',
    data() {
      return {
        ingredients: '',
      }
    },
    methods: {
      addToList() {
        //Splitting the text into lines
        var lines = this.ingredients.split(/\r?\n/);
        console.log(lines)
        for (var i = 0; i < lines.length; i++) {
          var words = lines[i].split(' ')
          if (Number(words[0])){
            console.log(words)
          }
        }
        this.ingredients = ''
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>