<template>
    <div class="formWrapper">
        <div class="article">
           <h2>Персональные данные</h2> 
        </div>        
        <div class="form">
            <label for="name">Имя</label>
            <input
                v-model="personalName"
                type="text"
                name="name"
                id=""
            >
        </div>
        <div class="form">
            <label for="last-name">Возраст</label>
            <input
                type="text"
                name="name"
                id=""
                v-model="pesonalLastName"
                @change="addPersonalInfo"
            >
        </div>
    </div>    
</template>

<script>
export default {
    name: "PersonalForm",
    methods: {
        addPersonalInfo () {
            let personalInfo = {
                name: this.personalName,
                age: this.pesonalLastName
            }
            this.$emit('add-personal-info', personalInfo)
        }
    }
}
</script>

<style>
.formWrapper {
    position: relative;
    width: 616px;
    margin: auto;
}
.form {
    position: relative;
    margin: 0 0 10px 0;
}
.form input {
    height: 56px;
    width: 96%;
    padding-left: 20px;
    font-size: 14px;
}
.form label {
    position: absolute;
    left: 21px;
    top: 10px;
    font-size: 13px;
    color: rgba(17, 17, 17, 0.48);
}
</style>