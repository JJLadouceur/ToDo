<template>
  <div class="container">
    <app-header :itemCount="items.length" :maxItems="maxItems"></app-header>
    <app-new-item @itemAdded="newItem"></app-new-item>
    <app-item-grid :items="items" @itemDeleted="deleteItem"></app-item-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Click an Item to clear it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import ItemGrid from './components/ItemGrid.vue';
import NewItem from './components/NewItem.vue';
import Header from './components/Header.vue';

export default {
  data: function(){
    return{
      items:["Add your ToDo's!"],
      maxItems: 10
    }
  },
  methods:{
    newItem(item){
      if(this.items.length >= this.maxItems){
        return alert('Catch up a bit before adding more ToDos')
      }
      this.items.push(item);
    },
    deleteItem(index){
      this.items.splice(index, 1);
    }
  },
  components: {
    appItemGrid: ItemGrid,
    appNewItem: NewItem,
    appHeader: Header
  }
}
</script>

<style>
</style>
