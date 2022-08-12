<script script="ts">
  import Button from './stories/Button.svelte'
  export let name

  import Main from './pages/Reservation.Remittance.Main.svelte'
  import Reg from './pages/Reservation.Remittance.Reg.svelte'
  import Detail from './pages/Reservation.Remittance.Detail.svelte'
  import NotFound from './pages/NotFound.svelte'
  import Router, { replace, push, pop } from 'svelte-spa-router'

  const routes = {
    '/': Main,
    '/reg': Reg,
    '/detail': Detail,
    '*': NotFound,
  }

  //   setTimeout(() => {
  //     replace('/reg')
  //   }, 3000)
</script>

<style lang="scss">
  @import 'App.scss';

  .App {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    .App {
      max-width: none;
    }
  }
</style>

<div class="App">
  <div class="App-header" />
  <h1>Hello {name}!</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <Router {routes} />
  <Button label="TEST" />
</div>
