<script>
  import { onMount } from 'svelte'
  import { gsap } from 'gsap'
  // import ScrollTrigger from 'gsap/ScrollTrigger'
  // gsap.registerPlugin(ScrollTrigger)

  import logo from './assets/svelte.png'
  import Counter from './lib/Counter.svelte'

  onMount(() => {
    gsap.from('h1', { x: 200 })
  })
</script>

<main>
  <img src={logo} alt="Svelte Logo" />
  <h1>Hello world!</h1>

  <Counter id="0" />
  <p>lets get this show on the road</p>
</main>

<style type="scss">
  @use 'styles/variables' as *;

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;

    img {
      height: 16rem;
      width: 16rem;
      border: 1px solid red;
    }

    h1 {
      color: #ff3e00;
      text-transform: uppercase;
      font-size: 4rem;
      font-weight: 100;
      line-height: 1.1;
      margin: 2rem auto;
      max-width: 14rem;
      @media (max-width: $minWidthSml) {
        max-width: none;
        background-color: plum;
      }
    }

    p {
      max-width: 14rem;
      margin: 1rem auto;
      line-height: 1.35;
      @media (max-width: $minWidthSml) {
        max-width: none;
        color: red;
      }
    }
  }
</style>
