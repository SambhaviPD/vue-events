<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div v-if="event">
        <h1>{{ event.title }} </h1>
        
        <div id="nav">
          <router-link :to="{ name: 'EventDetails' }"
            >Details | </router-link>
  
          <router-link :to="{ name: 'EventRegister' }"
            >Register | </router-link>
  
          <router-link :to="{ name: 'EventEdit' }"
            >Edit</router-link>
  
        </div>
        <router-view :event="event" />
    </div>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue'
  import EventService from '@/services/EventService.js'
  
  const event = ref(null)
  const props = defineProps({
    id: {
      required: true,
    },
  })
  
  onMounted(() => {
      // fetch event by id and set local data
      EventService.getEvent(props.id)
      .then((response) => {
        event.value = response.data
      })
      .catch((error) => {
        console.log('error: ', error)
      })
  })
  </script>
  