<template>
  <div class="card-block">
    <div class="card__info" >
      <span class="card__block-name">{{name}}</span>
      <span class="card__block-rate">{{code}}</span>
    </div>
    <div class="card__values">
      <span class="card__block-name">{{rate}}</span>
      <span class="card__block-rate">{{prevRate}}</span>
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
  flex-direction: column;
  justify-content: center;
  background-color: #e5d8d8;
  color: #000;
  border-color: #42b983;
  width: 73rem;
  border-radius: 1rem;
  padding: 1rem;

}


.card__info{
  display: flex;
  justify-content: center;

}

</style>