<template>
    <div class="formWrapper">
        <div class="article">
           <h2>Дети (Макс.5)</h2>
           <button @click="addNewChild">+ Добавить ребенка</button> 
        </div>  
        <div v-for="item in items" :key="item.id">
            <div class="inputWrapper">
                    <div class="formInp">
                        <label for="name">Имя</label>
                        <input
                            v-model="childName"
                            type="text"
                            name="name"
                        >
                    </div>
                    <div class="formInp">
                        <label for="age">Возраст</label>
                        <input
                            v-model="childAge"
                            v-on:change="addNewChildObject"
                            type="text"
                            name="age"
                        >
                    </div>
                    <p class="deleteButton" @click="deleteChild">Удалить</p>
            </div>
        </div>   
    </div>    
</template>

<script>
export default {
    name: "ChildrenForm",
    props: {
        items: []
    },
    methods: {
        addNewChild () {
            this.$emit('push-new-element')
        },
        deleteChild () {
            this.$emit('delete-element')
        },
        addNewChildObject () {
            let childObject = {
                name: this.childName,
                age: this.childAge
            }
            this.$emit('push-new-child-object', childObject)
        }
    }
}
</script>

<style>
.formWrapper {
    position: relative;
    width: 616px;
    margin: auto;
    margin-bottom: 44px;
}
.formInp {
    position: relative;
    margin: 0 0 10px 0;
    display: flex;
}
.inputWrapper {
    display: flex;
    justify-content: space-between;
}
.formInp input {
    height: 56px;
    width: 225px;
    padding-left: 20px;
    font-size: 14px;
}
.formInp label {
    position: absolute;
    left: 21px;
    top: 10px;
    font-size: 13px;
    color: rgba(17, 17, 17, 0.48);
}    
.deleteButton {
    color: #01A7FD;
    margin-top: 20px;
    cursor: pointer;
}

.article {
    margin-bottom: 20px;
    display: flex;
    justify-content: space-between;
}
.article button {
    border-radius: 30px;
    background: #fff;
    cursor: pointer;
    width: 204px;
    height: 44px;
    color: #01A7FD;
    border: 0.5px solid #01A7FD;
    margin-top: 5px;
}
</style>