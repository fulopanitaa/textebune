<template>
  <div class="contact">
    <div v-if="formAvailable">
      <form>
        <h4 class="text-center">{{title}}</h4>
        <label for="nume" class="capitalize">nume:</label>
        <input v-model="data.nume" id="nume" name="name" type="text" placeholder="nume" aria-required="true" aria-invalid="false">
        <span v-if="nameTooLong" class="alert">Name is too long. Maxlength is 3.</span>
        <label for="email" class="capitalize">email:</label>
        <input id="email" name="email" type="email" placeholder="email" aria-required="true" aria-invalid="false">
        <span class="alert"></span><label for="msg" class="capitalize">mesaj:</label>
        <textarea id="msg" name="message" placeholder="mesaj" class="pleft10px" aria-required="true" aria-invalid="false">
        </textarea><span class="alert"></span>
        <button type="submit">TRIMITE</button>
      </form>
      <section class="subscribe">
        <form>
          <h4>Newsletter</h4>
          <label for="newsletter-email">email:</label>
          <input id="newsletter-email" name="email" type="email" placeholder="email" aria-required="true" aria-invalid="false">
          <span class="alert"></span>
          <button type="submit" >SUBSCRIBE</button>
        </form>
      </section>
    </div>
    <p v-else>Contact form is not available</p>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data () {
    return {
      data: {
        nume: ''
      },
      nameTooLong: false,
      title: 'Adreseaza-ne o intrebare',
      formAvailable: true
    }
  },
  watch: {
    data: {
      handler ({ nume }, oldvalue) {
        this.nameTooLong = nume.length > 3
      },
      deep: true
    }
  },
  destroyed () {
    // window.alert('Are you sure?')
  },
  mounted () {
    setTimeout(() => {
      this.formAvailable = false
    }, 1000)
  }
}
</script>

<style scoped lang="scss">
  *{
  box-sizing: border-box;
  }
div.contact form{
  max-width: 600px;
  padding: 0px 20px;
  margin: auto;
  display:block;
  h4{
    font-size: 20px;
    font-weight: 400;
    text-align: center;
    padding: 30px;
  }
  label{
    display: block;
    padding: 12px 0 6px;
    text-align: left;
    text-transform: capitalize;
  }
  input, textarea{
    border:1px solid grey;
    height: 36px;
    padding-left: 8px;
    width: 100%;
    font-size: 14px;
    border-radius: 3px;
  }
  textarea{
    height: 140px;
    padding-top: 8px;
    resize: none;
  }
  button{
    border-radius: 3px;
    padding: 10px 40px;
    margin-top: 24px;
    background-color: #50c607;
    font-size: 18px;
    color: #fff;
    float: right;
    margin-left: auto;
  }
}
</style>
