<template>
  <div id="app">
    <header>
      <div class="logo">
        <a href="/about" >
          <img alt="logo" height="76px" width="123px" src="./assets/logotb.jpg">
        </a>
      </div>
      <div>
        <nav>
          <router-link v-for="(item, route) in menu" :key="item" :to="'/' + route">{{ item }}</router-link>
        </nav>
      </div>
      <div class="logo logo-fb">
      <a href="#/" id="logofb">
        <img alt="logo" height="32px" width="32px" src="./assets/logoFB.png">
      </a>
      </div>
    </header>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      menu: {
        about: 'About',
        events: 'Events',
        video: 'Video',
        press: 'Press',
        news: 'News',
        contact: 'Contact'
      }
    }
  }
}
</script>
<style lang="scss">
#app {
  font-family: 'Langar', cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
header{
  display: flex;
  height:76px;
  justify-content: space-between;
  border-bottom: 1px solid lightgray;
  width:100%;
  letter-spacing:-1px;
    .logo{
      width: 10%;
      position:relative;
      a{
        height:100%;
      }
      #logofb {
        position:absolute;
        top: 15px;
        right: 20px;
      }
    }
    > div{
      width:80%;
      text-align: center;
      font-size: 30px;
    }
  nav {
    padding: 20px;
    a {
      color: #2c3e50;
      text-decoration: none;
      text-transform: uppercase;
      background: transparent;
      -webkit-box-orient: horizontal;
      -webkit-box-direction: normal;
      -ms-flex-direction: row;
      flex-direction: row;
      z-index: 10;
      font-size: 20px;
      margin: 20px;

      &.router-link-exact-active {
        font-weight: bold;
        border-bottom:1px solid black;
      }
    }
  }
}

</style>
