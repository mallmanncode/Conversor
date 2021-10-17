<template>

  <div class="box">
      <Logo />
  <div class="seletor">
      <b-select v-model="moedaA" placeholder="USD" rounded>
                    <option value="USD">Dólar Americano - USD</option>
                    <option value="AUD">Dólar australiano  - AUD</option>
                    <option value="CAD">Dólar canadense  - CAD</option>
                    <option value="BTC">Bitcoin - BTC</option>
                    <option value="EUR">Euro - EUR</option>
                    <option value="GBP">Libra esterlina  - GBP</option>
                    <option value="JPY">Yen  - JPY</option>
                    <option value="CNY">Yuan  - CNY</option>
                    <option value="CHF">Franco suiço  - CHF</option>
                    
                </b-select>
                </div>
                <div class="texto">
                      <h1>  para Real {{moedaB}}</h1>
                </div>
                      <div class="valor">
                          
            <b-input v-model="moedaA_value" type="number" :placeholder="moedaA" rounded></b-input>
            </div>
            <div class="botao">
    <b-button type="is-info" @click="converter">Converter</b-button>
    </div>
    <h2>{{moedaB_value}} {{DePara}}</h2>
    </div>


</template>

<script>
import Logo from '@/components/logo.vue'

  export default {

    name: "Conversor",
    components: {
         Logo
     },
    props:     
     [
        'moedaB'
     ],

     


    data(){
        return {
            moedaA_value: "",
            moedaB_value: "0",
            DePara: "",
            moedaA: "",
        }
    },

    methods: {


        converter(){
            const DePara = this.moedaA + "_" + this.moedaB;
            const url = 
            "https://free.currconv.com/api/v7/convert?q="+
             DePara 
             +"&compact=ultra&apiKey=25f1450b7b6a85e3a6cf";

        fetch(url)
            .then(res => {
            return res.json();
            })
             .then(json => {       
                    const cotacao = json[DePara];
                    this.moedaB_value = parseFloat(cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                });


        }
    }



};
  
</script>

<style scoped>


.box {
    padding: 20px;
    max-width: 500px;
    box-shadow: 0 10px 10px 0 rgba(0, 0, 0, 5.2);  
    background-color: rgb(255, 255, 255);
    display: center;
}
.texto {
    display: center;
}
.botao{
    display: center;
    margin-left: 10px;
    padding-top: 10px;
}
.seletor{
    display: flex;
    margin-left: 10px;
}
.valor{
    display: flex;
    margin-left: 10px;
}

h1 {
    color: rgb(0, 110, 255);
    font-family: 'Roboto', sans-serif;    
    padding: 8px;
    margin-left: 10px;
}


h2 {
    color: rgb(0, 110, 255);
    font-family: 'Roboto', sans-serif;
    font-size: 30px;
    text-shadow: 0 10px 10px 0 rgba(0, 0, 0, 10.2);   
}

</style>
