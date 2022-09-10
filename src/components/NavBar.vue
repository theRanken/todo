<template>
    <div class="container">
        <header>
            <div class="brand">
                <h1 >TODO APP</h1>
            </div>
            <nav>
                <span class="nav-item">
                    <img src="" width="50" height="40" alt="user image">
                    <a class="nav-link" href="#">username</a>
                </span>  
            </nav>
        </header>
    </div>
</template>


<script>
export default{
     name: 'NavBar',
     data(){
         return{

         }
     } 
}
</script>

<style scoped>
.container{
    width: 100%;
    background: linear-gradient(to bottom right, #0050F0, #007284);
    color: #fafafa;
}
header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding: 1.5% 10%;
}

a{color: inherit; text-decoration: none}



@media (max-width:720px) {
}

</style>
