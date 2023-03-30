<template>
  <div id="container" class="grid grid-cols-3 space-x-12">   
    <div class="col-span-1">
      <form class="rounded-3xl ml-12 py-12" @submit.prevent="submitForm">
          <div class="space-y-6">
              <label for="name"></label>
              <input class=" rounded-lg px-6 py-2" type="text" v-model="name" id="name" placeholder="Name" required>
          </div>
          <div class="space-y-6">
              <label for="email"></label>
              <input class=" rounded-lg px-6 py-2" type="email" v-model="email" id="email" placeholder="Email" required>
          </div>
          <div class="space-y-6">
              <label for="phone"></label>
              <input class=" rounded-lg px-6 py-2" type="tel" v-model="phone" id="phone" placeholder="Phone Number (+27)" required>
              <span v-if="!valid"></span>
          </div>
          <div class="space-y-6">
              <label for="message"></label>
              <textarea class=" rounded-lg px-6 py-2 h-28" id="message" v-model="message" placeholder="Message" required></textarea>
          </div>
          <button class="mt-6 bg-white h-10 rounded-lg" type="submit">Submit</button>
      </form>
    </div>
    <div id="text" class="col-span-2 bg-white bg-opacity-75 rounded-3xl">
      <h2 class="text-2xl">Looking for me</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Form',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#container{

  height: auto;

  form{
    background-color: rgba($color: #FFDB58, $alpha: 1.0);
    height: auto;
  
    input, textarea{
      width: 75%;
      background: rgba($color: #ffffff, $alpha: .75);
    }
  
    button{
      width: 45%;
    }
  }

  #text{
    width: 90%;
  }
}
</style>
