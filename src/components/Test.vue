<template>
    <p :style="selected">Hello {{name}}</p><br/>
    <p>{{currentTimee()}}</p><br/>
    <input type="checkbox" v-model="checkboxchecked" id="changeColor" value="checkedBox"/>
    <label for="changeColor">Change Color</label><br/><br/>
    <input v-model="name">
    <button v-on:click="clearName()">clear</button>
    <button v-on:click="changeToUpperCase()">Caps On</button>
    <br/><br/>
    <label for="colorDropDown">Choose a color</label>
    <select v-model="selected" id="colorDropDown">
        <!-- inline object literal -->
        <option v-bind:value="{ color: 'red' }">Red</option>
        <option v-bind:value="{ color: 'blue' }">Blue</option>
        <option v-bind:value="{ color: 'yellow' }">Yellow</option>
        <option v-bind:value="{ color: 'black' }">Black</option>
    </select>
</template>
<script>
    export default{
        name:'Test',
        data(){
            return{
                name:"",
                currentTime:"",
                checkboxchecked:"",
                selected: '',
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