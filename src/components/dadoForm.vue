<template>
  <div id="dado-form-container">
    <label for="min">Mínimo</label>
    <input class="quantidade" id="min" type="number" min="1" v-model="valorMinimo" @change="valorMinimoSelecionado">
    <label for="max">Máximo</label>
    <input class="quantidade" id="max" type="number" v-model="valorMaximo">
    <input class="rolar-btn" type="button" value="Rolar" @click="rolarDados">
    <label id="resultado">
        <object :data="resultadoSVG" width="50px" height="50px" ></object>
    </label>
  </div>
</template>

<script>
export default {
    name: 'dadoForm',
    data(){
        return {
            valorMinimo: 1,
            valorMaximo: 6,
            resultadoSVG: null,
            dice: [
                {
                    value: "1",
                    svg: "../src/assets/dice/dice1.svg"
                },
                {
                    value: "2",
                    svg: "../src/assets/dice/dice2.svg"
                },
                {
                    value: "3",
                    svg: "../src/assets/dice/dice3.svg"
                },
                {
                    value: "4",
                    svg: "../src/assets/dice/dice4.svg"
                },
                {
                    value: "5",
                    svg: "../src/assets/dice/dice5.svg"
                },
                {
                    value: "6",
                    svg: "../src/assets/dice/dice6.svg"
                },
            ]
        }
    },
    methods: {
        valorMinimoSelecionado() {
            console.log(this.valorMaximo);
        },
        rolarDados() {
            let res = Math.floor(Math.random() * (this.valorMaximo - this.valorMinimo +1) + this.valorMinimo);
            console.log(res);
            this.resultadoSVG = this.dice[res-1].svg
        }
    }
}
</script>

<style scoped>
    #dado-form-container {
        display: flex;
        flex-direction: column;
        background-color: #e3d5ca;
        width: 250px;
        padding: 10px;
        border-radius: 5px;
        border: 2px solid #d5bdaf;
        box-shadow: 2px 2px 8px 0px #333;
    }

    #dado-form-container label {
        margin: 5px auto;
        font-weight: bold;
        font-size: 23px;
    }

    #dado-form-container .quantidade {
        height: 23px;
        font-size: 20px;
        text-align: center;
        width: 80px;
        margin: 0 auto;
        border: 2px solid #d5bdaf;
        border-radius: 5px;
    }

    #dado-form-container .rolar-btn {
        font-family: 'Roboto', sans-serif;
        font-size: 20px;
        font-weight: bold;
        width: 100px;
        margin: 10px auto;
        border: 2px solid #d5bdaf;
        background-color: #d6ccc2;
        border-radius: 5px;
        cursor: pointer;
        transition: .5s;
    }

    #dado-form-container .rolar-btn:hover {
        background-color: #edede9;
    }

    #dado-form-container .rolar-btn:active {
        background-color: rgb(151, 151, 151);
    }
</style>