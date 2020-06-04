<template>
  <div>
    <h1>{{ msg }}</h1>
    <!-- <img v-for="image in this.images" :src="image.url" :key="image.name"/> -->
    <img :src="test['hamburger']" />
    <img :src="test['apple']" contain height="100px" width="100px"/>
  </div>
</template>

<script>
import foodData from './foodResponse.json'

export default {
  name: 'list',
  data () {
    return {
      msg: 'List all recipe',
      images: [
        {
          url: require('../assets/logo.png'),
          name: 'logo'
        },
        {
          url: require('../assets/hamburger.png'),
          name: 'hamburger'
        }
      ],
      jsonData: foodData,
      test: {
        'logo': require('../assets/logo.png'),
        'hamburger': require('../assets/hamburger.png'),
        'apple': require('../assets/image/Apple.svg')
      }
    }
  },

  beforeMount () {
    console.log(foodData)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
