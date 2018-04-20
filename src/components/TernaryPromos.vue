<template>
  <section class="promos">
    <div class="columns">
      <div class="column" v-for="promo in promos" :key="promo['jcr:title']">
        <picture>
          <source v-bind:srcset="promo['thumbnailDesktop']" media="(min-width: 600px)">
          <source v-bind:srcset="promo['thumbnailMobile']" media="(min-width: 600px)">
          <img v-bind:src="promo['thumbnailTablet']" v-bind:alt="promo['jcr:title']">
        </picture>
        <h3>{{ promo['jcr:title'] }}</h3>
        <p>{{ promo['teaserText'] }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Ternary',
  props: {
    collections: {}
  },
  data: function () {
    return {
      promos: {}
    }
  },
  mounted () {
    this.getHero()
  },
  methods: {
    getHero: function () {
      let collectionArray = Object.assign(this.collections)
      let promosArray = []
      // Lets sort
      collectionArray.sort(function (a, b) {
        var dateA = new Date(a.articleDate)
        var dateB = new Date(b.articleDate)
        return dateA - dateB
      })
      // Reverse the array so we have the newest colelction at position 0
      collectionArray.reverse()

      // Lets loop through our collections and grab 3 right after the main hero
      for (var i = 0; i < collectionArray.length; i++) {
        // Make sure we only grab 1,2,3 out of the array
        if (i >= 4) {
          promosArray.push(collectionArray[i])
        }
      }
      console.log(promosArray)
      // Lets save our first collection to be used as a hero
      this.promos = promosArray
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
