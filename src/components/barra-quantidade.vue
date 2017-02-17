<template>
    <div class="row">
        <div class="col-md-12">
            <div class="col-md-12 barra barra-fundo">
                <div class="col-md-12 barra barra-frente" :style="estilo">{{quantidade}}/10</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props:{
          quantidade: {
              type: Number
          }
        },
        data(){
            return{

            }
        },
        computed:{
            estilo(){
                let cor;
                if (this.quantidade == 10){
                    cor = 'red';
                }
                else{
                    cor='blue';
                }

                return `width: ${this.quantidade * 10}%; background-color: ${cor}`
            }
        }
    }
</script>