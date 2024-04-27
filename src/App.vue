<template>
  <div class="container">
    <MyHeader phoneName="PHONEZONE" authorName="Vaishnavi Kommi" />
    <PhoneBox :phones="phones" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import PhoneBox from './components/PhoneBox.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    PhoneBox
  },
  data(){
    return {
      phones: []
    }
  },
  methods: {
  async fetchphones() {
    try {
      const res = await fetch('https://nodejs-phonezone.onrender.com/api');
      if (!res.ok) {
        throw new Error('Failed to fetch data');
      }
      const data = await res.json();
      this.phones = data.PhoneDetails; 
      console.log(this.phones);
    } catch (error) {
      console.error(error);
    }
  }
},
async created() {
  await this.fetchphones();
}

 

}
</script>


<style>


@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Montserrat', sans-serif;
}

.container {
  max-width: 1350px;
  height: 600px;
  margin: 30px auto;
  overflow: auto;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}


</style>
