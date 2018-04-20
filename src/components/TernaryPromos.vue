<template>
  <div class="ternary-promos">
    <div class="columns is-multiline">
      <div class="column is-half-tablet is-one-quarter-desktop" v-for="promo in promos" :key="promo['jcr:title']">
        <div class="ternary-promo">
          <img v-bind:src="promo['thumbnailMobile']" v-bind:alt="promo['jcr:title']">
          <div class="ternary-promo-inner">
            <a v-bind:href="promo['jcr:path']" target="_blank">
              <h3>{{ promo['jcr:title'] }}</h3>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
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
        var dateA = Date.parse(a.articleDate)
        var dateB = Date.parse(b.articleDate)
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
.ternary-promos {
  padding: 3rem 0;

  .column {
    text-align: center;

    .ternary-promo {
      position: relative;
      line-height: 0;
      img {
        width: 100%;
      }
      .ternary-promo-inner {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        display: flex;
        a,a:visited {
          display: flex;
          width: 100%;
          flex-direction: column;
          justify-content: center;
          background-color: rgba(0, 0, 0, 0.2);
          padding: 0 15%;
          color: #fff;
          transition: all .2s ease-in;
        }
        a:hover {
          background-color: #EB2B1E;
        }
        h3 {
          font-weight: 600;
          text-align: center;
          letter-spacing: .02em;
          line-height: 1.1;
          text-transform: uppercase;
        }
      }
    }
  }
}
</style>
