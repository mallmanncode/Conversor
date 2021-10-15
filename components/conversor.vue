<template>

  <div class="box">
      <div class="seletor">
      <b-select v-model="moedaA" placeholder="USD" rounded>
                    <option value="USD">USD</option>
                    <option value="BTC">BTC</option>
                </b-select>
                      <h1>Para {{moedaB}}</h1>
                      </div>
                      <div class="outro">
      <b-field>
            <b-input v-model="moedaA_value" type="number" :placeholder="moedaA" rounded></b-input>
        </b-field>
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

.seletor{
    padding: 20px;
    max-width: 300px;
    display: flex;
    


}
.box {
    padding: 20px;
    max-width: 600px;
    box-shadow: 0 10px 10px 0 rgba(0, 0, 0, 5.2);  
    background-color: rgb(207, 207, 207);
    display: flex;
    margin-left: 200px;
    background-image: url('~/assets/img/fundo.png');
    background-position: 0 -50px;
    background-size: cover;
    
}

.outro {
    padding: 20px;
    max-width: 150px;
    display: center;
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
