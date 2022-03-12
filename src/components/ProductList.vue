
<template>
<div class="wrapper">
  <div class="athletes">
    <div class="athlete" v-for="athlete in athletes" :key="athlete.id">
      <div class="info">
        <h1>{{athlete.name}}</h1>
        <p>{{athlete.weight}}</p>
      </div>
      <div class="image">
        <img :src="'/images/athletes/'+athlete.image">
      </div>
      <div class="record">
        <h2>{{athlete.record}}</h2>
        <button @click="addToCompare(athlete)" class="auto">Compare Athletes</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'AthleteList',
  props: {
    athletes: Array
  },
  methods: {
      addToCompare(athlete) {
          let exist = false;
          this.$root.$data.compare.forEach(item => {
            if (item.id == athlete.id) {
                exist = true;
            } 
          });
          if (!exist) {
            athlete.quantity = 1;
            this.$root.$data.compare.push(athlete);
          }
          else {
            athlete.quantity++;
          }
      }
  }
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
.athletes {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
.athlete {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}
.athlete img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}
.athlete .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}
.info {
  background: ##696969;
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
.record {
  display: flex;
}
button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}
.auto {
  margin-left: auto;
}
</style>
