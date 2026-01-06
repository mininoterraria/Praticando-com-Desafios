01. Crie um programa que verifica se uma palavra ou frase é um palíndromo.
```js
    //Regras:
        //Ignorar acentos/pontuações.
        //Ignorar espaços.
        //Ignorar maiusculo/minusculo.

/*
let caracteresOriginal = prompt("Insira uma palavra/frase/intervalo numérico palíndromo:");
let tratarPontuacoes = caracteresOriginal.normalize("NFD").replace(/[\u0300-\u036f\u0021-\u002F\u003A-\u0040\u005B-\u0060\u007B-\u007E]/g, "");
let tratarCaseEspaco = tratarPontuacoes.toLowerCase().replace(/\s+/g, "").trim();
let caracteresTrasParaFrente = tratarCaseEspaco.split('').reverse().join('');

caracteresOriginal = tratarCaseEspaco;

if(caracteresOriginal === caracteresTrasParaFrente){
    alert("Sim, é palíndromo!");
}else{
    alert("Não é palíndromo!");
}
```
02. Crie um programa com uma função que receba três números como argumentos e os retorne em ordem crescente. Exiba os números ordenados.
```js
function compararValores(a, b){
    return a - b;
}

function ordemCrescente(num1,num2,num3){
    const arrayNumeros = [num1,num2,num3];
    return arrayNumeros.sort(compararValores);

}

console.log(ordemCrescente(14,22,10));
```
03. Crie um formulário simples com campos de entrada e utilize JavaScript para recuperar os valores digitados nos campos usando a propriedade value. Exiba os valores no console e na tela.
```html
<html>
<body>
<form id="meuForm">
    <label for="campoNome">Nome:</label>
    <input type="text" id="campoNome" name="nome">
    
    <label for="campoIdade">Idade:</label>
    <input type="text" id="campoIdade" name="idade">

    <button type="button" onclick="capturarValores()">Capturar Valores</button>
  
  <div id='mostraNomeIdade'><span>Seu nome e idade irão aparecer aqui.</span></div>
</form>

<script>
    function validarInputIdade(idade){
      const regex = /^[0-9]\d*$/;

      return regex.test(idade);
  }

  function limparCampoIdade(){
      return document.getElementById('campoIdade').value = '';
  }

  function capturarValores(){
      let nome = document.getElementById('campoNome').value;
      let idade = document.getElementById('campoIdade').value;

      let validacao = validarInputIdade(idade);

      if(validacao){
          console.log(nome);
          console.log(idade);

          let exibirNomeIdade = document.getElementById('mostraNomeIdade').querySelector('span');
          exibirNomeIdade.textContent =  `Seu nome é ${nome} e sua idade é ${idade}`;
      }else{
          alert("Idade inválida, insira apenas valores inteiros positivos.");
          limparCampoIdade();
      }
      
  }
</script>
</body>
</html>
```
04. Tenha um elemento HTML na página (por exemplo, um parágrafo) e utilize JavaScript para modificar seu conteúdo usando a propriedade textContent.
```html
<html>
    <body>
<p id="meuParagrafo">Texto original</p>
<button onclick="modificarConteudo()">Modificar Conteúdo</button>

<script>
    function modificarConteudo(){
      document.getElementById('meuParagrafo').textContent = 'Conteúdo modificado!';
  }
</script>
  </body>
</html>
```
05. Faça a soma de duas variáveis numéricas e apresente no console com uma mensagem amigável em Template String.
```js
const num1 = 2;
const num2 = 3;

console.log(`A soma dos números ${num1} e ${num2} acima é igual a ${num1 + num2} `);
```
06. Receba, no mínimo, duas sentenças como uma string e utilize split() para quebrá-la em frases menores com base em um ponto e vírgula como delimitador.
```js
const duasSentencas = "Criar o que não existe ainda deve ser a pretensão de todo sujeito que está vivo; A tarefa mais importante de uma pessoa que vem ao mundo é criar algo";
const separarSentencas = duasSentencas.split(';');

console.log(separarSentencas);
```
07. Receba uma string contendo números separados por vírgulas. Utilize split() para separar os números e exibi-los no console.
```js
const string = '1,2,3,4,5';
const numerosSeparados = string.split(',');
console.log(numerosSeparados);
```
08. Crie uma função que aceite uma string como parâmetro, utilize a função parseInt para converter essa string em um número inteiro e retorne o resultado.
```js
function converterStringEmInteiro(string){ //Função que converte uma string em valor numérico, isso se possível.
    const regex = /^-?\d+$/;

    if(!regex.test(string)){
        alert("Não é possível fazer a conversão, insira apenas valores numéricos inteiros.");
    }else{
        string = parseInt(string);
        console.log(string);
    }

}

converterStringEmInteiro('-2');
```
09. Escreva um programa de calculadora simples com funções separadas para adição, subtração, multiplicação e divisão. Utilize um bloco condicional para determinar qual função executar com base em uma variável que representa a operação desejada.
```js
function adicao(numero1,numero2){ //Função que faz a adição dos números escolhidos.
    return numero1 + numero2;
}

function subtracao(numero1,numero2){ //Função que faz a subtração dos números escolhidos.
    return numero1 - numero2;
}

function multiplicacao(numero1,numero2){ //Função que faz a multiplicação dos números escolhidos.
    return numero1 * numero2;
}   

function divisao(numero1,numero2){ //Função que faz a divisão dos números escolhidos.
    if(numero2 === 0){
        return 'Não é possível dividir por zero.';
    }else{
        return numero1 / numero2;
    }
    
}

function validarOperacaoInserida(operacao){ //Função que valida o tipo de operação inputada pelo usuário.
    const regex = /^[+\-*\/]$/;
    const validarRegex = regex.test(operacao);
   
    if(validarRegex){
        return operacao;
    }else{
        alert("Operação inserida inválida!");
        return;
    }
}


function selecionarOperacao(numero1, numero2, operacao){ //Função que seleciona a operacação de acordo com o símbolo inputado pelo usuário.
    if(operacao === '+'){
        return adicao(numero1, numero2);
    }else if(operacao === '-'){
        return subtracao(numero1, numero2);
    }else if(operacao === '*'){
        return multiplicacao(numero1,numero2);
    }else{
        return divisao(numero1, numero2);
    }
}

function validarNumeroInserido(numero, tipoNumero){ //Função que valida o número inserido pelo usuário.
    if(numero || numero === ''){
        //const regex = /^-?\d+(\.\d+)?$/;
        const validarRegex = regex.test(numero);

        if(validarRegex){
            numero = Number(numero);
            if(numero === 0 || numero !== 0){
                return numero;
            }   

        }else{
            alert(`Valor inserido para ${tipoNumero} é inválido! Insira apenas o símbolo de uma das 4 operações matemáticas!`);
            return;
        }

    }

}

function exibirResultado(numero1, numero2, operacao, resultado){ //Função que exibe o resultado da operação.
    alert(`O resultado de ${numero1} ${operacao} ${numero2} é: ${resultado}`);
}

function calculadora(){ //Função principal que controla o fluxo de toda aplicação.
    let numero1 = prompt("Insira o primeiro número:"); 
    let numero2 = prompt("Insira o segundo número:");
    let operacao = prompt("Qual operação deseja realizar? (+) / (-) / (*) / (/)");
    
    numero1 = validarNumeroInserido(numero1, 'numero1');
    numero2 = validarNumeroInserido(numero2, 'numero2');
    operacao = validarOperacaoInserida(operacao);

    if(typeof(numero1) === 'number' && typeof(numero2) === 'number' && operacao){
        
        const resultado = selecionarOperacao(numero1, numero2,operacao);

        exibirResultado(numero1, numero2, operacao, resultado);
    }
}

calculadora(); //Chamada da função que executará toda aplicação.
```
10. Implemente uma função que aceite um número como parâmetro e utilize um bloco condicional para determinar se o número é par ou ímpar.
```js
function determinarTipoNumero(numero){
    if(isNaN(numero) || numero === ''){
        alert("Isso não é um número!");
        return;
    }

    numero = Number(numero);

    if(numero % 1 === 0){
        if(numero % 2 === 0){
            alert("É par!");
        }else{
            alert("É ímpar!");
        }
    }else{
        alert("Insira apenas valores inteiros!");
    }

    
}

determinarTipoNumero(5);
```
11. Crie uma função que converta a temperatura de Celsius para Fahrenheit e vice-versa. Utilize uma variável para indicar a escala desejada e um bloco condicional para determinar qual conversão realizar
```js
function celsiusParaFahrenheit(temperatura){ //Função que converte celsius para fahrenheit.
    const fahrenheit = (temperatura * 1.8) + 32;
    return fahrenheit;
}

function fahrenheitParaCelsius(temperatura){ //Função que converte fahrenheit para celsius.
    const celsius = (temperatura - 32) * 5/9;
    return celsius;
}

function validarTemperatura(temperatura){ //Função que valida a temperatura inputada pelo usuário.
    const regex = /^\s*-?\d+(?:[.,]\d+)?\s*$/;
    const testeRegex = regex.test(temperatura);

    if(testeRegex){
        temperatura = temperatura.replace(',','.');
        temperatura = Number(temperatura);
        return temperatura;
    }else{
        alert("Insira apenas valores numéricos!");
        return;
    }

}

function validarTipoConversao(tipoConversao){ //Função que valida o tipo de escala escolhido pelo usuário.
    const regex = /^[CcFf]$/;
    const testeRegex = regex.test(tipoConversao);
    
    if(testeRegex){
        return tipoConversao;
    }else{
        alert("Valor inserido no tipo de conversão é inválido!");
        return;
    }
}

function definirEscala(temperatura, tipoConversao){ //Função que define a escala de acordo com o input de tipo escolhido pelo usuário.
    if(tipoConversao === 'C' || tipoConversao === 'c'){
        return fahrenheitParaCelsius(temperatura);
    }else{
        return celsiusParaFahrenheit(temperatura);
    }
}

function exibirResultado(temperatura, escalaEscolhida, tipoConversao,){ //Função que faz a exibição correta do resultado dependendo da escolha de escala.
    if(tipoConversao === 'C' || tipoConversao === 'c'){
        alert(`A conversão da temperatura em ${temperatura} °F  para Celsius é: ${escalaEscolhida.toFixed(2)} °C`);
    }else{
        alert(`A conversão da temperatura em ${temperatura} °C  para Fahrenheit é: ${escalaEscolhida.toFixed(2)} °F`);
    }
}

function conversorTemperatura(){ //Função principal da aplicação.
    let temperatura = prompt("Insira a temperatura desejada:");
    let tipoConversao = prompt("Qual conversão quer fazer? (C) - Fahrenheit para Celsius OU (F) - Celsius para Fahrenheit.");

    temperatura = validarTemperatura(temperatura);
    tipoConversao = validarTipoConversao(tipoConversao);
    
    if(typeof(temperatura) === 'number' && tipoConversao){
        const escalaEscolhida = definirEscala(temperatura, tipoConversao);
        const resultadoConversao = exibirResultado(temperatura, escalaEscolhida, tipoConversao);
    }
}

conversorTemperatura();  //Chamada da função que ativa toda a aplicação.
```
12. Adicione os números 1,2,3 em uma variável chamada minhaLista e armazene os números 4, 5 e 6 separadamente em outra variável. Use o método concat() para combinar as sequências de valores em uma nova lista chamada novaLista. Imprima novaLista no console.
```js
const minhaLista = [1,2,3];
const numeros = [4,5,6];

const novaLista = minhaLista.concat(numeros);

console.log(novaLista);


    //. Remova o último elemento de minhaLista. Imprima minhaLista após a remoção.
novaLista.pop();
console.log(novaLista);

    //. Utilize o algoritmo de Fisher-Yates (também conhecido como Knuth Shuffle) para embaralhar os elementos em novaLista. Pesquise e adapte o código para realizar o embaralhamento.

function embaralharLista(lista){
    for (let indice = lista.length; indice; indice--) {

        const indiceAleatorio = Math.floor(Math.random() * indice);

        
        [lista[indice - 1], lista[indiceAleatorio]] = [lista[indiceAleatorio], lista[indice - 1]];
            
    }

    console.log(lista);
}

embaralharLista(novaLista);
```
13. Crie uma função chamada removerDuplicatas que aceita um array como parâmetro e retorna um novo array sem elementos duplicados.
```js
const arrayDuplicado = [1,2,2,3,3];

function removerDuplicatas(array){
    return [...new Set(array)];
}

const novoArray = removerDuplicatas(arrayDuplicado);

console.log(novoArray);
```
14. Crie uma função que valide se um número é positivo, negativo ou zero.
```js
function validarNumero(){
    let numero = prompt("Insira um número qualquer:");
    const regex = /^[+-]?(?:\d+[.,]?\d*|[.,]\d+)$/;
    const regexTeste = regex.test(numero);

    if(regexTeste){
        numero = Number(numero.replace(',','.'));
    }else{
        alert("Valor inputado é inválido!");
        return
    }

    if(numero > 0){
        alert("É positivo!");
        
    }else if(numero < 0){
        alert("É negativo!");

    }else if(numero === 0){
        alert("É zero!");speechSynthesis
    }
}

validarNumero();
```
15. Implemente uma função que verifique se uma pessoa é maior de idade.
```js
function verificarIdade(){
    let idade = prompt("Insira sua idade:")
    const regex = /^[0-9]+$/;
    const testeRegex = regex.test(idade);

    if(testeRegex){
        idade = Number(idade);
    }else{
        alert("Valor inserido é inválido!");
        return;
    }


    if(idade >= 18){
       alert("É de maior!"); 
    }else{
        alert("É de menor!");
    }
}

verificarIdade();
```
16. Desenvolva uma função que valide se uma string é vazia ou não.
```js
function validarString(){
    const string = prompt("Insira qualquer coisa:");

    if(string.trim().length === 0){
        alert("Sim, é uma string vazia!");
    }else{
        alert("Não é uma string vazia!");
    }
    
}

validarString();
```
17. Crie uma função que determine se um ano é bissexto
```js
function validarAnoBissexto(){
    let ano = prompt("Insira qualquer ano:");
    const regex = /^[0-9]+$/;
    const regexTeste = regex.test(ano);

    if(regexTeste){
        ano = Number(ano);
    }else{
        alert("Valor inserido é inválido!");
        return;
    }

    if(ano % 4 === 0){
        if(ano % 100 !== 0){
            alert("É bissexto!");
        }else if(ano % 100 === 0 && ano % 400 === 0){
            alert("É bissexto!");
        }else{
            alert("Não é bissexto!");
        }   
    }else{
        alert("Não é bissexto!");
    }

}

validarAnoBissexto();
```
18 Implemente uma função que calcule a média de dois números, interrompendo a execução se algum dos números não for válido.
```js
function mediaNumeros(){
    let numero1 = prompt("Insira o primeiro número:");
    let numero2 = prompt("Insira o segundo número:");
    const regex = /^[+-]?(?:\d+[.,]?\d*|[.,]\d+)$/;
    const regexTeste1 = regex.test(numero1);
    const regexTeste2 = regex.test(numero2);

    if(regexTeste1 && regexTeste2){
        numero1 = Number(numero1);
        numero2 = Number(numero2);
        const media = (numero1 + numero2) / 2;

        alert(`A média dos números ${numero1} e ${numero2} é: ${media.toFixed(2)}`);
    }else{
        alert("Um ou mais valores inválidos inseridos!");
    }
}

mediaNumeros();
```
19. Desenvolva uma função que receba um array como parâmetro e retorne o seu tamanho.
```js
const listaNumeros = [13,32,47];

function comprimentoArray(array){
    return array.length;
}

console.log(`O comprimento do array é: ${comprimentoArray(listaNumeros)}`);

comprimentoArray(listaNumeros);
```
20. Crie um array e utilize a função includes para verificar se um elemento específico está presente.
```js
const listaPalavras = ['banana','aveia','peixe'];

if(listaPalavras.includes('banana')){
    alert("Elemento incluso!");
}else{
    alert("Elemento não incluso!");
}
```
21. Implemente uma função que receba um array e um elemento, e retorne se o elemento está presente no array.
```js
const arrayElementos = ['feijao',2,'banana',15];

function validarElementoNoArray(array,elemento){
    if(array.includes(elemento)){
        return `Está presente!`;
    }else{
        return `Não está presente!`;
    }
}
alert(validarElementoNoArray(arrayElementos,2))
```
22. Crie um array de strings e utilize includes para verificar se uma determinada string está presente.
```js
const arrayStrings = ['banana','feijao','arroz'];
const verificacao = arrayStrings.includes('feijao');

if(verificacao){
    alert("Está presente!");
}else{
    alert("Não está presente!");
}
```
23. Desenvolva uma função que receba um array de objetos representando estudantes de um curso e um objeto que representa um estudante procurado. Depois retorne se o objeto está presente no array
```js
const alunos = [
    {nome: 'Daniel'},
    {nome: 'Danilo'},
    {nome: 'Danubio'}
]

const alunoProcurado = {nome: 'Daniel'};


function buscarObjeto(arrayObjetos,alunoProcurado){
    for(const chave of arrayObjetos){
        if(chave.nome === alunoProcurado.nome){
            return `Aluno está presente no array de objetos!`;
        }
    }
    return `Aluno não está presente no array de objetos!`;
}

alert(buscarObjeto(alunos, alunoProcurado));
```
24. Crie uma função que receba um array de números e retorne a soma dos elementos pares e o produto dos elementos ímpares.
```js
const arrayNumeros = [1,2,3,4,5,6,7,8,9,10];

function somaprodutoElementos(arrayNumeros){ 
    let numerosPares = 0;
    let numerosImpares = 1; 

    for(const numero of arrayNumeros){
        if(numero % 2 === 0){
            numerosPares += numero;
        }else{
            numerosImpares *= numero;
        }
    }

    const resultado = `A soma dos elementos pares é: ${numerosPares} e o produto dos elementos ímpares é: ${numerosImpares}`;

    return resultado;
}

console.log(somaprodutoElementos(arrayNumeros));
```


