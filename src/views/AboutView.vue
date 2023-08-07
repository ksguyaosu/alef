<template>
  <div class="about">
    <div class="title" v-for="personal in personal" :key="personal.name">
      <p>Персональные данные</p>
      <h1>{{ personal.name }}, {{ personal.age }} лет</h1>
    </div>    
    <div class="children">
      <p>Дети</p>
      <div v-for="child in child" :key="child.name" class="childrenBlock">
        <h2>{{ child.name }}, {{ child.age }} лет</h2>
      </div>     
    </div>
  </div>
</template>

<script>
  export default {
    name: 'about',
    props: {
      items: [],
      child: [],
      personal: []
    }
  }
</script>

<style>
  .about {
    width: 200px;
    position: absolute;
    left: 375px;
    margin-top: 30px;
  }
  .title {
      margin-bottom: 40px;
  }  
  .title p {
    text-align: left;
    font-size: 16px;
  } h1 {
    font-size: 16px;
  }
  .childrenBlock {
    width: 144px;
    height: 44px;
    background: #F1F1F1;
    text-align: center;
  } h2 {
    font-size: 14px;
    padding: 12px;
  }
  .children p {
    text-align: left;
  }
</style>