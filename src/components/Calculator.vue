<template>
    <div class=" h-screen bg-blue-400 flex justify-center py-16 ">
        
        <div class="w-1/4">

            <div class=" p-3 text-right shadow-2xl rounded-t-lg bg-white border-blue-900">
                <p class=" font-semibold text-gray-700 h-6">{{Operacion}}</p>
                <p class=" font-bold text-3xl text-gray-900 my-2">{{Resultado}}</p>
            </div>

            <div class="grid grid-cols-4 grid-5 shadow-2xl rounded-b-lg">

                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 col-span-2 hover:bg-blue-600"@click="clickAC()">AC</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="clickDel()">DEL</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-500 border-blue-600 hover:bg-gray-800"@click="click('÷')">÷</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('7')">7</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('8')">8</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('9')">9</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-500 border-blue-600 hover:bg-gray-800"@click="click('-')">-</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('4')">4</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('5')">5</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('6')">6</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-500 border-blue-600 hover:bg-gray-800"@click="click('+')">+</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('1')">1</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('2')">2</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('3')">3</button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-500 border-blue-600 hover:bg-gray-800 "@click="click('x')">x</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 col-span-2 hover:bg-blue-600"@click="click('0')">0</button>
                <button class=" h-16 text-xl text-white font-semibold bg-blue-500 border-blue-400 hover:bg-blue-600"@click="click('.')">.<div class=""></div></button>
                <button class=" h-16 text-xl text-white font-semibold bg-gray-500 border-blue-600 hover:bg-gray-800"@click="clickResultado()">=</button >
            </div>

        </div>
 
    </div>
</template>

<script>

export default {
    data (){
        return{
            Operacion:'',
            Resultado:'0',
        }
    },


    methods: {

        clickAC(){
            this.Resultado ='0';
        },

        clickDel(){
            if (this.Resultado.length > 1) {
                this.Resultado = this.Resultado.substring(0, this.Resultado.length -1);
            } else {
                this.Resultado = '0';
            }
        },

        click(par){
            if (this.Resultado == '0') {
                this.Resultado = par;
            } else {
                this.Resultado += par;
            }
        },

        clickResultado(){
            let operacion = this.Resultado;
            this.Operacion = operacion;

            operacion = operacion.replace('x', '*');
            operacion = operacion.replace('÷', '/');
            
            
            this.Resultado = eval(operacion);
            

        }
    },

}
</script>

<style scoped>
    button {
        border: 1px solid black
    }
    
</style>
