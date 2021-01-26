<template>
  <div>
    <BaseTitle>
      <span>Events</span>
      <span style="color: blue;">&nbsp;today</span>
    </BaseTitle>
    <div v-for="(event, index) in events" :key="index">
      <EventCard :coverimg="event.coverimg" :text="event.text" :thumbs="event.thumbs" website="www.google.ro">
        <span>THIS IS SOME CUSTOM FOR THIS PAGE</span>
      </EventCard>
    </div>
  </div>
</template>

<script>
import EventCard from '../components/EventCard'
import BaseTitle from '../components/BaseTitle'
export default {
  name: 'Events',
  components: {
    EventCard,
    BaseTitle
  },
  data () {
    return {
      events: [
        { text: 'Lorem ipsum dolor', coverimg: 'article.jpg', thumbs: ['a1.jpg', 'a2.jpg', 'a3.jpg', 'a4.jpg'] },
        { text: 'Hi', coverimg: 'article.jpg', thumbs: ['a1.jpg', 'a2.jpg', 'a3.jpg', 'a4.jpg'] }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
</style>
