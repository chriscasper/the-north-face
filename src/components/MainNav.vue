<template>
  <nav class="navbar is-transparent is-fixed-top" role="navigation" aria-label="main navigation">
    <div class="container">
      <div class="navbar-brand">
        <a class="navbar-item" href="https://bulma.io">
          <img src="../assets/logo-tnf.svg" alt="The North Face®" width="100" height="100">
        </a>

        <a role="button" class="navbar-burger" data-target="navbarMainMenu" aria-label="menu" aria-expanded="false">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div id="navbarMainMenu" class="navbar-menu">
        <div class="navbar-start">
          <a class="navbar-item" href="/">Women's</a>
          <a class="navbar-item" href="/">Mens's</a>
          <a class="navbar-item" href="/">Kids'</a>
          <a class="navbar-item" href="/">Shoes</a>
          <a class="navbar-item" href="/">Equipment</a>
          <a class="navbar-item" href="/">Collections</a>
          <a class="navbar-item" href="/">Athletes</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'MainNav',
  data () {
    return {
      something: ''
    }
  },
  mounted () {
    // Lets setup the hamburger menu
    document.addEventListener('DOMContentLoaded', function () {
      // Get all "navbar-burger" elements
      var $navbarBurgers = Array.prototype.slice.call(document.querySelectorAll('.navbar-burger'), 0)

      // Check if there are any navbar burgers
      if ($navbarBurgers.length > 0) {
        // Add a click event on each of them
        $navbarBurgers.forEach(function ($el) {
          $el.addEventListener('click', function () {
            // Get the target from the "data-target" attribute
            var target = $el.dataset.target
            var $target = document.getElementById(target)
            // Toggle the class on both the "navbar-burger" and the "navbar-menu"
            $el.classList.toggle('is-active')
            $target.classList.toggle('is-active')
          })
        })
      }
    })
    // End Hamburger
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
