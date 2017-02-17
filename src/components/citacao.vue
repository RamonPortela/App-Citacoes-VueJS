<template>
    <div class="citacao">
        <p>{{mensagem}}</p>
    </div>
</template>

<script>
export default{
    props:{
        mensagem: {
            type: String,
            required: true
        }
    },
    data() {
        return{

        }
    }
}
</script>

<style>

</style>