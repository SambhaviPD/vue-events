<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div v-if="event">
        <p>Register an event here</p>
    </div>
  </template>
  
  <script>
    export default {
      props: ['event']
    }
  </script>
  