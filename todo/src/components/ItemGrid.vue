<template>
  <div class="row">
    <app-quote v-for="(item, index) in items" @click.native="deleteItem(index)">{{ quote }}</app-quote>
  </div>
</template>

<script>
import Item from "./Item.vue";

export default {
  props: ["items"],
  components: {
    appItem: Item
  },
  methods:{
      deleteItem(index){
          this.$emit('itemDeleted', index);
      }
  }
}
</script>

<style>
</style>
