<template>

  <div class="box">

      <h1> {{moedaA}} Para {{moedaB}}</h1>
      <b-field type="is-info">
            <b-input v-model="moedaA_value" v-bind:placeholder="moedaA"></b-input>
        </b-field>
    <b-button type="is-light" inverted outlined value="Converter" @click="converter">Converter</b-button>
    <h2>{{moedaB_value}} {{DePara}}</h2>
    




    </div>


</template>
</template>

<script>
  export default {

    name: "Conversor",
    props: [
        "moedaA",
        "moedaB"
        ],

    data(){
        return {
            moedaA_value: "",
            moedaB_value: 0,
            DePara: "",
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
                    this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(
                        2
                );
                });


        }
    }



};
  
</script>

<style scoped>

.box {
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);    
}

h1 {
    color: rgb(241, 16, 193);
}

h2 {
    color: blue;
}

.button {
    color: rgb(255, 0, 149);
}
</style>
