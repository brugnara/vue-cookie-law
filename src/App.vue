<template>
  <div id="app">
    <select v-model="theme">
      <option value="base">Base</option>
      <option value="blood-orange">Blood Orange</option>
      <option value="dark-lime">Dark Lime</option>
      <option value="royal">Royal</option>
      <option value="base--rounded">Base Round</option>
      <option value="blood-orange--rounded">Blood Orange Round</option>
      <option value="dark-lime--rounded">Dark Lime Round</option>
      <option value="royal--rounded">Royal Round</option>
    </select>
    <cookie-law :theme="theme" position="top" transition-name="fade"></cookie-law>
    <cookie-law :theme="theme">
      <div slot-scope="props" class="container">

        <button class="skew" @click="props.accept"><span>I accept</span></button>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ex, hic?
        </p>

        <button class="skew" @click="props.close"><span>Close</span></button>
      </div>

    </cookie-law>
  </div>
</template>

<script>
import CookieLaw from './components/CookieLaw'

export default {
  name: 'app',
  components: {
    CookieLaw
  },
  data () {
    return {
      theme: 'base'
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  margin-top: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
}

select {
  width: 400px;
  height: 40px;
  font-size: 18px;
}

.skew {
  background: rebeccapurple;
  color: #fff;
  font-size: 0.875rem;
  font-weight: 700;
  text-transform: uppercase;
  border-radius: 8px 0;
  transform: skew(-20deg);
  padding: 0.2rem 1rem;
}

.skew span {
  display: inline-block;
  transform: skew(20deg);
}

.container {
  width: 100%;
  text-align: center;
}
</style>
