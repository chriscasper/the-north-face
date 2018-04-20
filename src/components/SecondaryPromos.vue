<template>
  <div class="secondary-promos">
    <div class="columns">
      <div class="column" v-for="promo in promos" :key="promo['jcr:title']">
        <div class="secondary-promo-con">
          <div class="promo-img-con">
            <img v-bind:src="promo['thumbnailMobile']" v-bind:alt="promo['jcr:title']">
            <div class="promo-img-con-inner">
              <a v-bind:href="promo['jcr:path']" target="_blank">
                <h3>{{ promo['jcr:title'] }}</h3>
              </a>
            </div>
          </div>
          <p>{{ promo['teaserText'] }}</p>
        </div>
        <a v-bind:href="promo['jcr:path']" target="_blank" class="button is-outlined">Explore Collection</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SecondaryPromo',
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
        if (i > 0 && i < 4) {
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
<style lang="scss" scoped>
  // Lets include just the utilities
  @import "~bulma/sass/utilities/_all";
  .secondary-promos {
    text-align: center;
    margin-bottom: 3rem;
    .secondary-promo-con {
      height: 14rem;
      @include mobile {
        height: auto;
      }
      @include fullhd {
        height: 16rem;
      }
      .promo-img-con {
        width: 100%;
        margin-bottom: 1rem;
        position: relative;
        line-height: 0;
        img {
          width: 100%;
        }
        .promo-img-con-inner {
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
            &:hover {
              background-color: #EB2B1E;
            }
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
      p {
        margin-bottom: 1.5rem;
        font-size: .8rem;
        padding: 0 .3rem;
      }
    }
    a.button {
      font-weight: 600;
      letter-spacing: .02em;
      text-transform: uppercase;
      margin: 0 auto;
    }
  }
</style>
