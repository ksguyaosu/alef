<template>
    <div class="wrapper">
        <div class="logo">
            <img src="../assets/Frame10.png" alt="">
        </div>
        
    </div>   
    <div class="links">
            <nav>
                <router-link to="/" class="link">Форма</router-link>
                <router-link to="/about" class="link">Превью</router-link>
            </nav>
    </div> 
    <hr>
</template>

<script>
    export default {
        name: "Layout"
    }
</script>

<style>
    .wrapper {
        display: flex;
    }
    .routerLinks {
        position: absolute;
        left: calc(50% - 90px);
    }
    .link {
        text-decoration: none;
        margin: 0 24px 24px;
        font-size: 14px;
        font-weight: 400;
    }
    .links {
        text-align: center;
    }
    .logo {
        position: absolute;
        top: 35px;
        left: 55px;
    }
    hr {
        width:100vw;
        margin: 0 -10px 0 -10px;
    }
</style>