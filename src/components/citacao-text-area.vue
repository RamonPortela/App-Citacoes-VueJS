<template>
    <div class="div-text-area centralizar">
        <div class="row">
            <div class="col-md-12"><h1>Citações</h1></div>
            <div class="col-md-12"><textarea name="citacoes" id="textAreaCitacoes" cols="30" rows="3" v-model="novaCitacao" @keydown.enter="criarNovaCitacao"></textarea></div>
        </div>
        <div class="row">
            <div class="col-md-12">
                <button class="btn btn-primary" @click="criarNovaCitacao">Criar Citação</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                novaCitacao: ''
            }
        },
        methods:{
            criarNovaCitacao(){
                this.$emit("criarNovaCitacao", this.novaCitacao);
                this.novaCitacao = '';
            }
        }
    }
</script>