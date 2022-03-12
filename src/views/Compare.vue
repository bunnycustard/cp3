

<template>
    <div>
        <CompareList :compare="compare" />
    </div>
</template>

<script>
import CompareList from "../components/CompareList.vue"
export default {
  name: 'CompareComp',
  components: {
    CompareList
  },
  data() {
    return {
    }
  },
  computed: {
    compare() {
      return this.$root.$data.compare;
    }
  },
}
</script>
