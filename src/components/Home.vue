<template>
  <div class="home">
    <Hero :collections=collectionObj v-if="collectionObj !== null"></Hero>
    <div class="container">
      <SecondaryPromos :collections=collectionObj v-if="collectionObj !== null"></SecondaryPromos>
    </div>
    <div class="container">
      <TernaryPromos :collections=collectionObj v-if="collectionObj !== null"></TernaryPromos>
    </div>
  </div>
</template>

<script>
import Hero from '@/components/Hero'
import SecondaryPromos from '@/components/SecondaryPromos'
import TernaryPromos from '@/components/TernaryPromos'

export default {
  name: 'Home',
  data () {
    return {
      collectionObj: null
    }
  },
  components: {
    Hero,
    SecondaryPromos,
    TernaryPromos
  },
  methods: {
    getCollections: function () {
      let self = this
      // Lets get the collection object
      fetch('/static/collections.js')
        .then(response => response.text())
        .then((data) => {
          // Lets save our data
          self.collectionObj = JSON.parse(data).hits
        })
        .catch(error => console.error(error))
    }
  },
  mounted () {
    this.getCollections()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

</style>
