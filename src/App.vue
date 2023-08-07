<template>
  <Layout />  
  <router-view
    v-bind:items="items"
    v-bind:child="child"
    v-bind:personal="personal"
    @push-new-element="recieveEmit"
    @delete-element="receieveDeleteEmit"
    @push-all-info="pushChildInfo"
  />  
  <Footer class="footer" />
</template>

<script>
  import Layout from "@/components/Layout.vue"
  import Footer from "./components/Footer.vue";

  export default {
    components: {
      Layout,
      Footer
    },
    data () {
      return {
        items: [
          {
            id: 1
          }
        ],
        child: [],
        personal: []
      }
    },
    methods: {
      recieveEmit () {
        if (this.items.length < 5) {
          this.items.push({id: Math.random() * 100})
        } else {
          alert('Вы можете добавить не больше 5 детей!')
        }
      },
      receieveDeleteEmit () {
        this.items.splice(1, 1)
      },
      pushChildInfo (child, personalInfo) {
        this.child = child
        this.personal = personalInfo
        console.log(personalInfo, 'app.vue');
      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #1111117A;
}

.footer {
  position: fixed;
  bottom: 0px;
  width: 101%;
  left: -5px;
  padding: 0;
  height: 76px;
  background: rgba(17, 17, 17, 0.1);
}
</style>
