<template>
  <NavBar />
  <AddForm @new-item-added="pushItem" />
  <div v-if="itemList.length">
    <ItemObject :itemList="itemList" @delete-item="deleteItem" @cross-out-item="crossOut"/>
  </div>
  <div class="message" v-else>
    <p> You Haven't Added Any Activities Yet</p>
  </div>

</template>

<script>
import NavBar from './components/NavBar.vue'
import AddForm from './components/AddForm.vue'
import ItemObject from './components/ItemObject.vue'

export default {
  name: 'App',
  data(){
   return{
     itemList:[],
   }
  },
  methods:{
    pushItem(item){
      this.itemList.push(item)
    },
    deleteItem(index){
      this.itemList.splice(index,1)
    },
    crossOut(index){
      if (this.itemList[index].crossedOut == false){
        this.itemList[index].crossedOut = true; 
      }else{
        this.itemList[index].crossedOut = false; 
      }
    },
  },
  components: {
    NavBar,
    AddForm,
    ItemObject,
  }
}
</script>

<style>
:root{
  --blue: #0050F0;
  --bg-gradient: linear-gradient(to top right, #0050F0, #007284);
  --info-gradient: linear-gradient(to top left, #1d76e2, #0c1593);
  --danger-gradient: linear-gradient(to top left, #910011, #dd002f);
  --btn-padding: 1em 2em;
  --color: #fff;
  --radius: 12px;
}
*{
  padding: 0;
  margin:0;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-border-box: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #212121;
  width:100%;
  
  position: relative;
}
body{
  background-color: #eeeeee;
  position: relative;
  max-width:100vw;
}

.btn{
  padding: var(--btn-padding);
  outline: none;
  border: none;
  border-radius: var(--radius);
  color: var(--color);
}

.message{
  width:100%;
  text-align:center;
  font-size: 2rem;
  font-weight: bold;
  padding: 10% 5%;
}


</style>
