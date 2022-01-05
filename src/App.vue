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
      // console.log(this.resp.Valute)
    }
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  width: 76rem;
}

.card{
  display: flex;
  flex-direction: column;
  width: 76rem;
  max-height: 400rem;
  background-color: #fcfbfb;
  border-radius: 1rem;
  box-shadow: 0 0 2px rgba(0,0,0,0.5);

}

.card__btn{
  padding: 1rem;
  border-radius: 1rem;
  border: none;
  max-height: 5rem;
  font-weight: bold;
  font-size: 3rem;
  width: 76rem;
  background: rgba(101, 155, 124, 0.86);
  color: white;
  cursor: pointer;
}

.card__btn:active{
  background: rgba(33, 59, 44, 0.86);
}

.list{
  padding: 0.4rem;
}
.list-elem{
  list-style-type: none;
  margin-bottom: 1rem;
}

</style>
