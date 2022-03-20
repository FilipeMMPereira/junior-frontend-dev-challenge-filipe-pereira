<template>
  <div class="main">
    <div v-for="item in 16" v-bind:key="item" v-bind:id="'eclipse'+item"></div>
  </div>
</template>

<script>
export default {};
</script>