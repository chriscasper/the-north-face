<template>
  <footer class="footer">
    <div class="container">
      <div class="columns">
      </div>
      <div class="columns">
        <div class="column is-narrow">
          <img class="logo" src="../assets/logo-tnf.svg" alt="The North Face®" width="100" height="100">
        </div>
        <div class="column copyright">
          <p>Ⓒ The North Face, A VF Company</p>
          <ul>
            <li><a target="_blank" href="http://www.vfc.com/california-transparency-in-supply-chains-act">CA Supply Chains Act</a></li>
            <li><a target="_blank" href="http://www.vfc.com/modern-slavery-act-disclosure-statement">UK Slavery Act</a></li>
            <li><a target="_blank" href="http://www.thenorthface.com/help/privacy.html">Privacy Policy</a></li>
            <li><a target="_blank" href="http://www.thenorthface.com/help/terms.html">Terms of Use</a></li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  footer.footer {
    border-bottom: 1px solid #EB2B1E;
    img.logo {
      max-height: 5rem;
      max-width: 5rem;
    }
    .copyright {
      font-size: .7rem;
      text-transform: uppercase;
    }
  }
</style>
