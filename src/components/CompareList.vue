<template>
<div class="wrapper">
  <div class="athletes">
    <div v-if="pNum === 0" classs="empty-compare">Add athletes to your comparison</div>
    <div v-else class="athlete" v-for="athlete in compare" :key="athlete.id">
      <div class="info">
        <h1>{{athlete.name}}</h1>
        <p>{{athlete.weight}}</p>
      </div>
      <div class="image">
        <img :src="'/images/athletes/'+athlete.image">
      </div>
      <div class="quantity">Quantity: {{athlete.quantity}}</div>
      <div class="record">
        <h2>{{athlete.record}} EA</h2>
        <button @click="removeFromCompare(athlete)" class="auto">Remove All</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CompareList',
  props: {
    compare: Array
  },
  computed: {
    pNum() {
        return this.$root.$data.compare.length;
    },
  },
  methods: {
    removeFromCompare(athlete) {
        this.$root.$data.compare.splice(this.$root.$data.compare.indexOf(athlete), 1);
    },
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
.empty-compare {
    font-size: 2em;
    font-weight: bold;
}
.athletes {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
.athletes {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}
.athletes img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}
.athletes .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}
.info {
  background: #7fd7f4;
  color: #000;
  padding: 10px 30px;
  height: 100px;
}
.info h1 {
  font-size: 16px;
}
.info h2 {
  font-size: 14px;
}
.info p {
  margin: 0px;
  font-size: 10px;
}
.quantity {
    color: #f26868;
    font-weight: bold;
}
.record {
  display: flex;
}
button {
  height: 50px;
  background: #f26868;
  color: white;
  border: none;
}
.auto {
  margin-left: auto;
}
</style>
