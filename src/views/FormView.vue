<template>
  <div class="home">
    <HelloWorld
      v-bind:items="items"
      @push-new-element="recieveEmit"
      @delete-element="receieveDeleteEmit"
      @push-child-info="pushAllInfo"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  props: {
    items: []
  },
  methods: {
    recieveEmit () {
      this.$emit('push-new-element')
    },
    receieveDeleteEmit () {
      this.$emit('delete-element')
    },
    pushAllInfo (child, personalInfo) {
      console.log(child, 'CHILD');
      console.log(personalInfo, 'personalInfo');
      this.$emit('push-all-info', child, personalInfo)
    }
  }
}
</script>
