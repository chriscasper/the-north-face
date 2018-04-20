<template>
  <div id="app">

    <MainNav/>

    <section class="line-promo">
      <div class="container">
        <h5>Free 3-Day Shipping &amp; Free Returns</h5>
      </div>
    </section>

    <router-view/>

    <Footer/>
  </div>
</template>

<script>
import MainNav from '@/components/MainNav'
import Footer from '@/components/Footer'

export default {
  name: 'App',
  components: {
    MainNav,
    Footer
  }
}
</script>

<style lang="scss">
// Set Brand Colours
$red: #EB2B1E; //#E72B1E SVG Logo Red varies from red used on site css
$pink: #FA7C91;
$brown: #757763;
$beige-light: #D0D1CD;
$beige-lighter: #EFF0EB;

// Update Bulma's global variables
$family-sans-serif: "Helvetica Neue", Helvetica, Arial, sans-serif;
$primary: $red;
$link: $red;

// Update some of Bulma's component variables
$control-border-width: 2px;
$input-background-color: $beige-lighter;
$input-border-color: transparent;
$input-shadow: none;

// Navbar
$navbar-height: 7rem;
$navbar-item-img-max-height: 5rem;

// Import the rest of Bulma
@import "~bulma";

// Line Promo
.line-promo {
  h5 {
    text-transform: uppercase;
    font-weight: bold;
    font-size: 1rem;
    letter-spacing: 0.1rem;
    padding: .25em 0;
    line-height: 1;
    color: #fff;
  }
  text-align: center;
  background-color: $red;
}
.column, .container {
  transition: all .2s ease-in;
}
</style>
