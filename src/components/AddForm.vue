<template>
    <div class="container">
        <div class="form" v-on:submit.prevent="newItemAdd">
            <form>
                <input id="title" v-model="title" type="text" class="form-input"> 
                <input type="submit" value="&plus; Add Item">
            </form>
        </div>
    </div>
</template>

<script>
export default {
    name:'AddForm',
    data(){
        return{
            title: '',
            date: new Date()
        }
    },
    methods: {
        newItemAdd(){
            let item = {
                title : this.title,
                time : `${this.date.getDate()}-${this.date.getMonth()}-${this.date.getFullYear()}`,
                crossedOut: false
            }
            this.$emit('new-item-added', item)
            this.title = ''
        }
    }
   
}
</script>

<style scoped>
.container{
    background-image: url(../assets/11.jpg);
    background-repeat: no-repeat;
    background-size:cover;
    width:100vw;
    padding: 10% 5% 2.5%;
}
.form{
    width:50%;
    margin:auto;
}
form{
    display:flex;
    justify-content:center;
    align-items:center;
    width:100%;
    margin:auto;
}
input{
    margin-left:1%;
    margin-right:1%;
}

input[type="submit"]{
    background:var(--bg-gradient);
    border:none;
    padding:var(--btn-padding);
    color:var(--color);
    font-weight:bold;
    border-top-right-radius:var(--radius);
    border-bottom-right-radius: var(--radius);    
}
.form-input{
    border: 1.5px solid var(--blue);
    width: 100%;
    padding: .90em 1.2em;
    border-top-left-radius:var(--radius);
    border-bottom-left-radius: var(--radius);
}
</style>
