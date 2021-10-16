<template>

  <div class="box">
  <div class="seletor">
      <b-select v-model="moedaA" placeholder="USD" rounded>
                    <option value="USD">Dólar Americano - USD</option>
                    <option value="BTC">Bitcoin - BTC</option>
                </b-select>
                </div>
                <div class="texto">
                      <h1>  Para {{moedaB}}</h1>
                </div>
                      <div class="valor">
            <b-input v-model="moedaA_value" type="number" :placeholder="moedaA" rounded></b-input>
        </b-field>
            </div>
            <div class="botao">
    <b-button type="is-info" @click="converter">Converter</b-button>
    <h2>{{moedaB_value}} {{DePara}}</h2>
    </div>

    </div>


</template>

<script>
  export default {

    name: "Conversor",
    props:     
     [
        'moedaB'
     ],

    data(){
        return {
            moedaA_value: "",
            moedaB_value: "",
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
    background-image: url('~/assets/img/fundo.png');
    background-size: cover;
    background-position: center;
    padding: 20px;
    max-width: 500px;
    box-shadow: 0 10px 10px 0 rgba(0, 0, 0, 5.2);  
    background-color: rgb(207, 207, 207);
    display: center;
}
.texto {
    display: flex;
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
    color: rgb(255, 255, 255);
    padding: 8px;
    margin-left: 10px;
    font-family:monospace;
}


h2 {
    color: rgb(255, 255, 255);
    font-family: 'Roboto', sans-serif;
    font-size: 30px;
    text-shadow: 0 10px 10px 0 rgba(0, 0, 0, 5.2);   
}

</style>
