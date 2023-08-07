<template> 
  <PersonalForm
    class="PersonalForm"
    @add-personal-info="addPersonalInfo"
  />
  <ChildrenForm
   v-bind:items="items"
      @push-new-element="receiveEmit"
      @delete-element="receieveDeleteEmit"
      @push-new-child-object="pushNewChildObject"
    /> 
  <button class="saveButton" @click="saveBTN">Сохранить</button>   
</template>

<script>

import PersonalForm from './PersonalForm.vue';
import ChildrenForm from './ChildrenForm.vue';

export default {
  name: 'HelloWorld',
  components: {
    PersonalForm,
    ChildrenForm
  },
  props: {
    items: []
  },
  data () {
    return {
      child: [],
      personalInfo: []
    }
  },
  methods: {
    receiveEmit () {
      this.$emit('push-new-element')
    },
    receieveDeleteEmit () {
      this.$emit('delete-element')
    },    
    pushNewChildObject (childObject) {
      this.child.push(childObject)
    },
    saveBTN () {
      this.$emit('push-child-info', this.child, this.personalInfo)
    },
    addPersonalInfo (personalInfo) {
      this.personalInfo.push(personalInfo)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.PersonalForm {
  margin-top: 30px;
}
.saveButton {
  position: relative;
  left: 33.5%;
  top: -20px;
  width: 118px;
  height: 44px;
  border-radius: 30px;
  color: #fff;
  background: #01A7FD;
  border: 0px solid black;
  cursor: pointer;
}
</style>
