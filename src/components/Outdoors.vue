<template>
  <div class="outdoors container is-fluid">
    <h2>GET CONNECTED. GET OUTDOORS. GET INVOLVED.</h2>
    <div class="columns">
      <div class="column is-5-desktop is-4-widescreen is-half-tablet is-offset-2-widescreen is-offset-1-desktop endurance">
        <img src="/static/EnduranceChallenge-callout.jpg" alt="The North Face Endurance Challenge" />
        <h4>The North Face Endurance Challenge</h4>
        <p>Ready for a challenge? Registration for The North Face Endurance Challenge Series are now open. Find an event in your region and sign up. Don't delay, these events will sell out.</p>
        <a class="button is-danger is-fullwidth" href="https://www.thenorthface.com/get-outdoors/endurance-challenge.html" target="_blank">Register Today</a>
      </div>
      <div class="column is-5-desktop is-4-widescreen is-half-tablet explore">
        <img src="/static/ExploreFund-callout.jpg" alt="Explore Fund Grants" />
        <h4>Explore Fund Grants</h4>
        <p>Explore Fund grants support nonprofit organizations working to inspire and enable the next generation of outdoor explorers and conservationists.  Learn more about the program and its results.</p>
        <a class="button is-danger is-fullwidth" href="https://www.thenorthface.com/about-us/outdoor-exploration/explore-fund.html" target="_blank">Learn More</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Outdoors'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .outdoors {
    padding: 3rem 0;
    text-align: center;
    h2 {
      font-size: 2em;
      font-weight: bold;
      letter-spacing: 0;
      text-align: center;
      color: #000;
      text-transform: uppercase;
      margin-bottom: 1.5rem
    }
    .column {
      img {
        margin-bottom: 1.5rem;
        width: 100%;
      }
      h4 {
        font-weight: 600;
        text-align: center;
        letter-spacing: .02em;
        line-height: 1.1;
        margin-bottom: .5em;
        text-transform: uppercase;
      }
      &.explore h4 {
        padding: 0 21%;
      }
      p {
        margin-bottom: 1.5rem;
        font-size: .8rem;
        padding: 0 .3rem;
      }
    }
  }
</style>
