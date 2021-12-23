<template>
  <div class="card-block">
    <div class="card__info" >
      <span class="card__block-name">{{name}}</span>
      <span class="card__block-name">{{rate}} ₽</span>

    </div>
    <div class="card__values">
      <span class="card__block-code">{{code}}</span>
      <span class="card__block-rate">{{prevRate}} ₽</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card.vue",
  props: {
    name: String,
    code: String,
    rate: Number,
    prevRate: Number,
  }
}
</script>

<style scoped>
.card-block{

  display: flex;
  /*flex-direction: column;*/
  justify-content: space-between;
  background-color: white;
  flex-direction: column;
  color: #070707;
  border-color: #42b983;
  width: 73rem;
  border-radius: 1rem;
  padding: 1rem;
  box-shadow: 0 0 6px rgba(0,0,0,0.5);
  margin-bottom: 1rem;


}

.card__block-name{
  font-size: 1.5rem;
}

.card__block-code{
  font-size: 1.7rem;
}


.card__info{
  /*display: flex;*/
  /*justify-content: center;*/
  display: flex;
  justify-content: space-between;
  align-content: center;

}

.card__values{
  display: flex;
  justify-content: space-between;
  margin-top: 0.4rem;

}

.card__block-code{
  font-weight: bold;
}

.card__block-rate{
  font-size: 1.2rem;
  color: #9fa3a6;

}

</style>