<template>
  <div class="about">
    <h1>The button has been clicked {{counter}} times</h1>
    <button v-on:click="increment('a')" >Increment Counter</button>
  </div>
</template>


<script>

export default {
  name: 'about',
  data: function() {
    return { counter: 0 }
  },
  methods: {
    increment: function (e) {
      this.counter ++;
    }
  }
}
</script>
