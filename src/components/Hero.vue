<template>
  <div class="hero">
    <div class="hero-container">
      <picture>
        <source v-bind:srcset="hero['thumbnailDesktop']" media="(min-width: 1920px)">
        <source v-bind:srcset="hero['thumbnailTablet']" media="(min-width: 1024px)">
        <img v-bind:src="hero['thumbnailMobile']" v-bind:alt="hero['jcr:title']">
      </picture>
      <div class="hero-inner">
        <a v-bind:href="hero['jcr:path']" target="_blank" class="hero-block-link">
          <h1 class="title">
            {{ hero['jcr:title'] }}
          </h1>
          <h2 class="subtitle">
            {{ hero.teaserText }}
          </h2>
        </a>
        <a v-bind:href="hero['jcr:path']" target="_blank" class="button is-outlined explore">Explore {{ hero['jcr:title'] }}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Hero',
  props: {
    collections: {}
  },
  data: function () {
    return {
      hero: {}
    }
  },
  mounted () {
    this.getHero()
  },
  methods: {
    getHero: function () {
      let collectionArray = Object.assign(this.collections)
      // Lets sort
      collectionArray.sort(function (a, b) {
        var dateA = new Date(a.articleDate)
        var dateB = new Date(b.articleDate)
        return dateA - dateB
      })
      // Reverse the array so we have the newest colelction at position 0
      collectionArray.reverse()
      // Lets save our first collection to be used as a hero
      this.hero = collectionArray[0]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  // Lets include just the utilities
  @import "~bulma/sass/utilities/_all";
  .hero {
    background-color: hsl(0, 0%, 96%);
    margin-bottom: 1.5rem;
    @include mobile {
      background-color: transparent;
      margin-bottom: 3rem;
    }
    .hero-container {
      width: 100%;
      max-width: 1344px;
      margin: 0 auto;
      position: relative;
    }
    picture {
      display: block;
      line-height: 0;
      img {
        width: 100%
      }
    }
    .hero-inner {
      transition: all .2s ease-in;
      @include tablet {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        display: flex;
      }
      @include mobile {
        text-align: center;
      }
      a.hero-block-link,a.hero-block-link:visited {
        padding: 0 15%;
        display: block;
        @include desktop-only {
          padding: 0 20%;
        }
        @include tablet {
          display: flex;
          width: 100%;
          flex-direction: column;
          justify-content: center;
          background-color: rgba(0, 0, 0, 0.1);
          padding: 0 15%;
        }
        @include mobile {
          padding: 3rem 15%;
        }
      }
      h1 {
        font-size: 5.385em;
        letter-spacing: 0.1rem;
        color: #fff;
        text-transform: uppercase;
        transition: all .2s ease-in;
        @include desktop-only {
          font-size: 4.385em;
        }
        @include tablet-only {
          font-size: 3.5em;
        }
        @include mobile {
          text-align: center;
          color: #000;
          font-size: 2.5rem;
        }
      }
      h2 {
        font-size: 1.5rem;
        font-weight: bold;
        color: #fff;
        transition: all .2s ease-in;
        @include tablet-only {
          font-size: 1.2em;
        }
        @include mobile {
          text-align: center;
          color: #000;
          font-size: 1rem;
          font-weight: normal;
        }
      }
      a.button.explore {
        display: none;
        @include mobile {
          display: inline-flex;
        }
      }
    }
  }
</style>
