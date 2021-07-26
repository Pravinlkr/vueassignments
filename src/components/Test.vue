<template>
    <p>Hello {{name}}</p><br/>
    <p>{{currentTimee()}}</p>
    <input v-model="name">
    <button v-on:click="clearName()">clear</button>
    <button v-on:click="changeToUpperCase()">Caps On</button>
</template>
<script>
    export default{
        name:'Test',
        data(){
            return{
                name:"",
                currentTime:""
            }
        },
        created(){
            this.currentTime = new Date().toLocaleString();
        },
        methods:{
            clearName(){
                this.name = "";
            },
            changeToUpperCase(){
                this.name = this.name.toUpperCase();
            },
            currentTimee(){
                this.currentTime = new Date().toLocaleString();
                return this.currentTime
            }
        }
    }
</script>

<style scoped>            
p{
    text-align: center;
}
</style>