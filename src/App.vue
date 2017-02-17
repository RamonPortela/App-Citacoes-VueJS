<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <barra :quantidade="quantidadeCitacoes"></barra>
      </div>
      <div class="row">
        <nova-citacao @criarNovaCitacao="novaCitacao"></nova-citacao>
      </div>
      <div class="row">
        <div class="col-md-3" v-for="(cit, index) in citacoes">
          <citacao :mensagem="cit" @click.native="excluirCitacao(index)"></citacao>
        </div>
      </div>

      <div class="row">
        <div class="alert alert-info col-md-12 div-informacao">
          <p>Clique no citação para deleta-la</p>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import citacao from './components/citacao.vue'
import barra from './components/barra-quantidade.vue'
import novaCitacao from './components/citacao-text-area.vue'

export default {
  name: 'app',
  data () {
    return {
      citacoes: [],
      quantidadeCitacoes: 0
    }
  },
  components: {
      'citacao': citacao,
      'barra': barra,
      'nova-citacao': novaCitacao
  },
  methods:{
    novaCitacao(citacao){
        if(this.quantidadeCitacoes < 10){
            this.citacoes.push(citacao);
            this.quantidadeCitacoes++;
        }
        else
            alert("Quantidade de citações exedida.");
    },
    excluirCitacao(index){
        this.citacoes.splice(index, 1);
        this.quantidadeCitacoes--;
    }
  }
}
</script>

<style>

</style>
