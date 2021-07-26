<template>
    <p :style="changeColorOfText()">Hello {{name}}</p><br/>
    <p>{{currentTimee()}}</p><br/>
    <input type="checkbox" v-model="checkboxchecked" id="changeColor" value="checkedBox"/>
    <label for="changeColor">Change Color</label><br/><br/>
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
                currentTime:"",
                checkboxchecked:"",
                redtext:{
                    color: 'red'
                },
                normaltext:{
                    color: 'black'
                }
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
            },
            changeColorOfText(){
                if(this.checkboxchecked == true){
                    return this.redtext;
                }else{
                    return this.normaltext;
                }
            }
        }
    }
</script>

<style scoped>            
p{
    text-align: center;
}
</style>