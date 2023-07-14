import BaseInput from '@/components/BaseInput.vue'

<h3>Name and Describe your Event</h3>

<BaseInput
    v-model="event.title"
    label="Title"
    type="text"
/>

<BaseInput
    v-model="event.description"
    label="Description"
    type="text"
/>

<BaseInput
    v-model="event.locatio"
    label="Location"
    type="text"
/>