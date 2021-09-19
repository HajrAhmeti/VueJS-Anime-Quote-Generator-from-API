<template>
  <div id="app">
          <Header :name="info.name" :age="info.age"/>
    <div class="container">
       <div class="center">
        <input type="text" v-model="query">
        <button class="bt1" v-on:click="getData">Submit </button>
     </div>
    </div>
      <SavedPeoples :saved="saved" />
  </div>
</template>


<script>
import axios from 'axios'
import 'bootstrap/dist/css/bootstrap.css'
import Header from './components/Header.vue'
import SavedPeoples from './components/SavedPeoples.vue'
  export default { 
  name: 'App',
  components: {
   Header,
   SavedPeoples
  },
  data () {
    return {
      info: [],
      query: '',
      saved:[]
    }
  },
   methods:{
     getData() { 
     axios
    .get('https://api.agify.io/?name='+this.query+'')
    .then(response => (this.info = response.data))
    this.saved = [...this.saved, this.info]
    this.query = '';
    }
   }

}
</script>


<style lang="scss">
:root{
    --primary: #D81E5B;
    --secondary: #8A4FFF;
    --tertiary: #32CBFF;
    --dark:#131a26;
    --light: #EEE;
    --grey: #848484;
  }

  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  }
  .center{
    display:flex;
    justify-content: center;
  }
  input{
    font-size:19px;
  }
  .bt1{
    background-color: var(--primary);
    color: var(--light);
    margin-left:20px;
    padding:2px 5px 2px 5px;
    font-size:25px;
  }
  .button-container{
    display:flex;
    justify-content: center;
    padding:0px 32px;
    margin: 64px auto;

    button{
      border:none;
      outline:none;
      background-color: var(--primary);
      padding:15px 32px;
      border-radius:99px;
      color: var(--light);
      font-size:28px;
      font-weight: 700;
      text-transform: uppercase;
      transition: 0.4s;

      &:hover{
        background-color: var(--secondary);
      }
    }
  }
</style>