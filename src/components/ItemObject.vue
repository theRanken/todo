<template>
    <div class="listContainer">
        <ul class="list">
            <li v-for="(item, index) in itemList" :key="index" class="list-item">
                <div class="item-info">
                    <h3 :class="{crossed: item.crossedOut}">{{item.title}}</h3>
                    <br>
                    <date>{{item.time}}</date>
                </div>
                <div class="item-commands">
                    <button @click="$emit('cross-out-item', index)" class="btn info"> CrossOut </button>
                    <button @click="$emit('delete-item', index)" class="btn danger"> Delete</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props:{
        itemList:{
            type:Array,
            required: true,
        },
    },
    name:'ItemObject',
}
</script>

<style scoped>

.listContainer{
    width:75%;
    max-width: 75vw;
    margin: 0 auto;
}
.list{
    width: 100%;
    height:400px;
    margin: 2.5% auto 0;
}
.list-item{
    display:flex;
    flex-wrap: wrap;
    justify-content:space-between;
    align-items:center;
    padding: 1.5rem 2rem;
    width:75%;
    margin:12px auto;
    background: #fff;
    box-shadow: 0px 5px 5px #bdbdbd;
    border-radius: var(--radius);
}

.btn{
    margin-left:5px;
    margin-right:5px;
    font-weight: bold;
}

.btn.info{
  background: var(--info-gradient);
  
}
.btn.info:hover, .btn.danger:hover{
    opacity: 0.6;
    cursor:pointer;
}
.btn.danger{
  background: var(--danger-gradient);
  color: var(--color);
}
.crossed{
    text-decoration: line-through;
}

</style>