<template>
    <p>Hello {{name}}</p><br/>
    <input v-model="name">
</template>
<script>
    export default{
        name:'Test',
        data(){
            return{
                name:""
            }
        }
    }
</script>

<style scoped>
p{
    text-align: center;
}
</style>