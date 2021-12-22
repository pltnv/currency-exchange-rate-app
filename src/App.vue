<template>
   <div id="app">


     <div class="card">
       <div class="card__request">
         <button class="card__btn" @click="makeReq" > Актуальный курс валют</button>
       </div>
       <ul v-if="resp" class="list">
         <li v-for="(item, id) in resp.Valute" :key="id" class="list-elem">
           <Card
               :name="item.Name"
               :code="item.CharCode"
               :rate="item.Value"
               :prev-rate="item.Previous"
           >
           </Card>





           <!--         {{item.Name}}-->
           <!--         {{item.CharCode}}-->
           <!--         {{item.Value}}-->
           <!--         {{item.Previous}}-->

         </li>

       </ul>


     </div>

   </div>



</template>

<script>
import Card from "./components/Card";



export default {

  name: 'App',
  components: {
    "Card" : Card,
  },

  data() {

    return {
      resp: '',



    }
  },
  methods: {
    makeReq() {
      fetch("https://www.cbr-xml-daily.ru/daily_json.js")
          .then((response) => response.json()).then(json => this.resp = json);
      console.log(this.resp.Valute)



    }
  }

}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;

  /*-moz-osx-font-smoothing: grayscale;*/
  text-align: center;
  /*color: #2c3e50;*/
  margin-top: 4rem;

}


.card{
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-content: center;
  width: 75rem;

  max-height: 400rem;
  /*!*max-width: 75rem;*!*/
  /*margin: 0 auto;*/
  /*position: absolute;*/
  /*top: calc(50% - 400px);*/
  /*left: 0;*/
  /*right: 0;*/
  /*border-radius: 30px;*/
  background-color: #f3eeec;
  /*!*padding: 30px;*!*/
  /*color: white;*/

}

.card__btn{
  padding: 1rem;
  border-radius: 1rem;
  border: none;
  max-height: 5rem;

  font-weight: bold;
  font-size: 3rem;
  width: 75rem;
  background: rgba(23, 20, 20, 0.86);
  color: white;
  cursor: pointer;
}



.list-elem{
  list-style-type: none;
  margin-bottom: 1rem;
}



</style>
