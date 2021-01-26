<template>
    <div>
      <div class="content-card flex flex-between m-auto">
        <div>
        <img class="h100" :src="require(`../assets/${coverimg}`)" alt="event main img">
        </div>
        <div class="flex column">
          <p class="text-left">{{text}}</p>
          <slot />
          <a :href="website">go</a>
          <ul class="flex flex-wrap flex-between">
            <li v-for="(imgName, index) in thumbs" :key="index" class="flex flex-between">
              <img class="w100" :src="require(`../assets/thumbs/${imgName}`)" alt="img gallery">
            </li>
          </ul>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    text: {
      type: String,
      required: false
    },
    coverimg: {
      type: String,
      required: false
    },
    thumbs: {
      type: Array,
      required: false
    },
    website: {
      type: String,
      required: false
    }
  }
}
</script>

<style scoped lang="scss">
  .content-card {
    border: 1px solid lightgrey;
    padding: 12px;
    & > div:first-child {
      height: 600px;
    }
    li {
      width: 48%;
      margin-bottom: 12px;
    }
  }
  @media only screen and (max-width: 1024px) {
    .content-card {
      flex-direction: column;
      max-width: 427px;
    }
  }
  @media only screen and (min-width: 1024px) {
    .content-card {
      max-width: 800px;
      div {
        width: 45%;
      }
      & > div:last-child {
        justify-content: space-between;
      }
    }
  }
</style>
