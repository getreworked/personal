<template>
  <section>
    <showcase v-for="item in work" :key="item.title" v-bind="item" />
  </section>
</template>

<style scoped lang="scss">
  
</style>

<script>
  // API
  import { getWork } from '@/api';
  
  // Components
  import Showcase from '@/components/Showcase';

  export default {
    components: {
      Showcase
    },

    data: () => ({
      work: []
    }),

    created () {
      getWork().then(({ data }) => this.work = data.data);
    }
  }
</script>