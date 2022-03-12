
<template>
<div>
  <div class="pure-menu pure-menu-horizontal">
    <ul class="pure-menu-list">
      <li class="pure-menu-item"><a @click="select('Bantamweight')" href="#" class="pure-menu-link">Bantamweight</a></li>
      <li class="pure-menu-item"><a @click="select('Featherweight')" href="#" class="pure-menu-link">Featherweight</a></li>
      <li class="pure-menu-item"><a @click="select('Lightweight')" href="#" class="pure-menu-link">Lightweight</a></li>
      <li class="pure-menu-item"><a @click="select('Welterweight')" href="#" class="pure-menu-link">Welterweight</a></li>
    </ul>
  </div>
  <AthleteList :athletes="athletes" />
</div>
</template>

<script>
import AthleteList from "../components/AthleteList.vue"
export default {
  name: 'BrowseComp',
  components: {
    AthleteList
  },
  data() {
    return {
      weight: '',
    }
  },
  computed: {
    athletes() {
      return this.$root.$data.products.filter(athlete => product.weight === this.weight);
    }
  },
  methods: {
    select(weight) {
      this.weight = weight;
    }
  }
}
</script>
