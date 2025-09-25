#atividade 7#
##flex:##
- flex-grow
- flex-shrink
- flex-basis


#atividade 8#
- pesquisar herança no css
##grid css##

grid-template-columns: fr e px
grid-template-rows: fr e px

gap
row-gap
column-gap

#container#
grid-template-areas
grid-column
grid-row  SPAN


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="grid-exercicio">
    <header>Header</header>
    <nav>Menu</nav>
    <main>Conteúdo</main>
    <aside>Sidebar</aside>
    <footer>Footer</footer>
</div>
</body>
</html>

.grid-exercicio {
    display: grid;
    grid-template-areas:
        "header header header"
        "nav main aside"
        "footer footer footer";
    grid-template-columns: 150px 1fr 200px;
    grid-template-rows: 60px 1fr 40px;
    gap: 15px;
    height: 100vh;
}
header { grid-area: header; background: #b3cde0; 
}
nav { grid-area: nav; background: #6497b1; }
main { grid-area: main; background: #005b96; color: #fff; }
aside { grid-area: aside; background: #03396c; color: #fff; }
footer { grid-area: footer; background: #011f4b; color: #fff; }

#aula 9:#
https://tailwindcss.com/docs/installation/tailwind-cli

#aula 10#
- javascript ES (pesquisar)
- w3school
- assinatura da funçao
- if - switch/case/ defaut
- verifique se usuario e senha estao corretos:
- pra testar resultados no terminal: node _arquivo_.js
- prompt-sync biblioteca
-  


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

<script>
//verifique se usuario e senha estao corretos:
let user = "admin";
let pass = "12345";

function verificar (user, pass) {
if( user === "admin" && pass === "12345"){
  console.log("sucesso");
}else{
  console.log("falhou");
}
};


//verificar com base na cor de um semaforo e de pedestre atravessando a rua se posso avançar mau carro

// let semaforoCarros = (verde, amarelo, vermelho);
// let faixaPedestre = (verde, vermelho);
// // let temPedestre = ()

// function avançar (faixaPedestre, semaforoCarros) =>{
//   if {faixaPedestre === verde
//     return false;

//   } else {
//     return true
//   };
// };

let cor = "verde";
let pedestreAtravessando = false;

if (cor === "verde" && !pedestreAtravessando === false){
  console.log("pode passar");
}else{
  console.log("pare!");
};

</script>

</body>
</html>


// console.log("testando")

//verificar se é maior de idade
// let idade = 18;
// if (idade <= 17){
//     console.log("menor de idade")
// }else{
//     console.log("maior de idade")
// };




//verificar se um valor esta dentro de um intervalo
function verificaIntervalo (a,b){
    if ( )
}





//verificar se o valor é par ou impar
// let numero = 5;
// function verificaImparOuPar (numero) {
//     if (numero % 2 === 0){
//         console.log("é par")
//     } else {
//         console.log("é impar")
//     }
// };


#aula 11#
vocabulario: instancia= objetos pre determinados/ vetor= array/ desestruturação= desempacotar objetos

null pointer/ exception/ null safety = refenciar mesmo qando vazio (ex: perfil?.nome?)

#desestruturação de objetos:#
ex:
const livro= {
 titulo: "js lindo",
 autor: "fulano"
}
cosnt  {titulo, autor} = livro; //desestruturando

ex2:
const arr= [10,12,30,40]
const [a,b] = arr;  //a=10, b=20

ex3:
//pulando itens
cosnt [, , x] = arr; lulando itens e criando "x"

ex4:
... = rest(resto dos itens)
const [head, ... tail] = arr; //pega o primeiro e o ultimo

ex5:
troca de variaveis/ valores
let m= 1, n= 2;
[m,n] = [n,m]

ex6:
const user = {
    id: "10",
    name_: joao,
    city: recife
}
newName = "teste"
const {id, name_: newName} = user;
const {state = "PE"} = user;

#spead operator# "..."
ex7:
const num1 = [1,2];
const num2 = [4,6];

const todosNums = [...num1, ...num2];

//criar copia
const copia = [num1];

//inserir num1 em nova variavel de dados
const novo = [0,1,2,...num1, 3,4];

//pegar o mumero maior
Math.max(...num1, ...num2) 

const items = [..."bia"]
console.log(items)

- exercicio em sala:
// const items = [..."bia"]
// console.log(items)

//objeto: pessoa, profissao
const identidade = {

  id: "joao",
  idade: "12"
}
const profissao = {

  trabalho: "professor"
}

//ciar um terceiro objeto que junta os dois primeiros

const novoRegistro = {...identidade, ...profissao}
console.log(novoRegistro)
----------

## criar construtores (object constructor)

function Person(primeiro, ultimo, idade, olhos) {
  this.primeiro = "primeiro",
  this.ultimo = "ultimo",
  this.idade = "idade",
  this.olhos = "olhos",
}

const pessoa1 = new Person ("bia", "carneiro", "32", "castanho");
--------

const carro = {
  marca: "tesla",
  modelo: "modelo 3"
}

for (const chave in carro)
console.log {$ ...  }

##Aula 12
//protocolo // https e http


const frutas = ["maçã", "banana", "uva"]; 

// for clássico
// for(... ; ...; ){}
for (let i = 0; i < frutas.length; i++){
  console.log(`Fruta ${i}: ${frutas[i]}`)
}
//com while:
let i =0;
while (i<frutas.length){
  console.log(`Fruta ${i}: ${frutas[i]}`)
  i++
}


// com iteração
const arrayNumbers = []
for(let value = 10; value <= 100; value += 10){
  arrayNumbers.push(value)
  console.log('Valor:' + value)
} //iterando, pulando de 10 em 10


//for of
// for(... of ...){}
for (let fruta of frutas){
  console.log(fruta)
}


// for in  
const frutaObj = {
  nome: "laranja",
  tipo: "cítrica",
  valor: 5
}

for (chave in frutaObj){
  console.log(chave + " - " + frutaObj[chave])
}

const numbers = [10, 20, 30, 40]
for (const index in numbers){
  console.log(numbers[index])
}

const usuario = {
  nome:"Leticia",
  idade: 30
}

//for.forEach(()=>{});
frutas.forEach((fruta, index)=>{
  console.log(fruta);
  console.log(index);
  console.log(`Fruta: ${fruta}`)
});   

// const frutasEmMaiusculo = frutas.map((fruta)=>{ fruta.toUpperCase() });
// console.log(frutasEmMaiusculo)

// //JSX
// function ListaFrutas() {
//   const frutas = ["maçã", "banana", "uva"]; 
//   return (
//     <ul>
//       {frutas.map((fruta, index) => (
//         <li key = "{index}">{fruta}</li>
//       ))}
//     </ul>
//   );
// }

//iteração funcional
const numeros = [1,2,3,4];

//map - cada elemento dobrado
//tranformar
const dobrados = numeros.map(n=> n * 2)

//filtro
const pares = numeros.filter(n=> n % 2 === 0)

//reduce  
acumulador, item, index e array                  //0 é o valor inicial do acumulador
const soma = numeros.reduce((acumulador, n)=> acumulador + n, 0)

//criar uma arrow function que retorna o cubo de um valor
//for.forEach(()=>{});

const retornaCubo = numeros.map(n=> n * n * n)
console.log(retornaCubo)

function conectar(host = "localhost", porta = "8080){
  //todo  
}



####Aula 13####

user.foreach((item)=>{
    if()
})


const users = [
  {
    nome: "Ana Silva",
    idade: 28,
    contato: {
      email: "ana.silva@email.com",
      telefone: "11987654321"
    },
    cidade: "São Paulo"
  },
  {
    nome: "Bruno Santos",
    idade: 35,
    contato: {
      email: "bruno.santos@email.com",
      telefone: "21912345678"
    },
    cidade: "Rio de Janeiro"
  },
  {
    nome: "Carla Oliveira",
    idade: 42,
    contato: {
      email: "carla.oliveira@email.com",
      telefone: "31998765432"
    },
    cidade: "Belo Horizonte"
  },
  {
    nome: "Daniel Lima",
    idade: 23,
    contato: {
      email: "daniel.lima@email.com",
      telefone: "71987654321"
    },
    cidade: "Salvador"
  },
  {
    nome: "Elisa Costa",
    idade: 30,
    contato: {
      email: "elisa.costa@email.com",
      telefone: "81912345678"
    },
    cidade: "Recife"
  },
  {
    nome: "Felipe Almeida",
    idade: 50,
    contato: {
      email: "felipe.almeida@email.com",
      telefone: "51998765432"
    },
    cidade: "Porto Alegre"
  },
  {
    nome: "Gabriela Fernandes",
    idade: 25,
    contato: {
      email: "gabriela.fernandes@email.com",
      telefone: "61987654321"
    },
    cidade: "Brasília"
  },
  {
    nome: "Henrique Rocha",
    idade: 38,
    contato: {
      email: "henrique.rocha@email.com",
      telefone: "41912345678"
    },
    cidade: "Curitiba"
  },
  {
    nome: "Isabela Pereira",
    idade: 33,
    contato: {
      email: "isabela.pereira@email.com",
      telefone: "85998765432"
    },
    cidade: "Fortaleza"
  },
  {
    nome: "João Martins",
    idade: 45,
    contato: {
      email: "joao.martins@email.com",
      telefone: "11912345678"
    },
    cidade: "São Paulo"
  }
];

// export default mockData;
// users.foreach((item)=>{
//     if(item.age>18){
//         console.log(`O usuário ${item.name} é maior.`)
//     }
// });

//construa uma fução que retorne quantos usuarios que moram em cada estado

//passar por cada item
//iterar se for positivo para o estado escolhido

//reduce
//abre e fecha chave
// users.forEach(element => {
//     if(element.cidade === "São Paulo"){
//         const iteraCidade = users.reduce((acc,users )=> acc + users , 0)
//         console.log(iteraCidade);
//     }
    
// });

const contaCidades = users.reduce((acc, user)=>{
    //
    //fallback :    acc[users.cidade] = (acc[user.cidade] || 0 ) + 1;
    //return acc;
    if(!acc[user.cidade]){
        acc[user.cidade] = 0;
    }
    acc[user.cidade] += 1;
    return acc;
},{});
console.log(contaCidades);
//  {} = é o valor inicial do objeto

//faça a média das idades
//soma e divide pelo user.length
// const somaIdades = users.reduce((acc, user) =>{
//     return acc + user.idade;
// }, 0);
// const mediaIdade = somaIdades / users.length;
//ou
const somaIdades = users.reduce((acc, user, index, array) =>{
    acc += user.idade;
    if(index === array.length-1){
        return acc/array.length
    }
    return acc;
    }, 0);

//filter
const numeros = [1,2,3,4,5];

const maiorQuevinteeCinco = users.filter(user => user.idade > 25);
console.log(maiorQuevinteeCinco.length)


function saudacao(nome){
    const mensagem = `Olá, ${nome}`

    function mostrarSaudacao(){
        console.log(mensagem);
    }
    return mostrarSaudacao;

}

const olaHeitor = saudacao("Heitor");
olaHeitor();

////////
//template literals = interpolação de string  variáveis
async e await
try, catch - then, catch, finally

//ex pra framework:
setLista([,,,lista, novoItem]);  //spred operator
//não modifica a lista inicial, cria uma nova


-------------------------------------
## Aula 14 ##
//endpoints/ recurços ou rotas/ middle ware/ query string/ 

- pragimetech.com (API)
- https://jsonplaceholder.typicode.com/

JSON

// //parse: strig json -> obj js
// //stringfy: obj js -> strinh json

// //EX1:
// const usuario = {    //obj js
//     id: 1,
//     nome: "maria",
//     ativo: true
// }

// const jsonString = JSON.stringify(usuario, null, 4);
// console.log(jsonString);


// //EX2:
// const jsonRecebido = '{ id": 1, "nome": "maria", "ativo": true }';

// try{
//     const dados = JSON.parse(jsonRecebido)
//     console.log(dados.nome)
//     console.log(dados.ativo)
// } catch (e){
//     console.error("Erro a processar json:", e.message)
// }

//EX3:

//GET
async function buscarUsuarios(id) {
    try{
      const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`)
      if(!res.ok){
        throw new Error(`Erro HTTP: ${res.status}`);
      }
      //console.log(res)   // vem as infos do pacote
      const dados = await res.json();
      console.log("Nome: ", dados.name)
      //console.log(dados)

    }catch(error){
      if(error.name === "SyntaxError"){
      console.error("Erro ao converter JSON:", error.message)
      }
      console.error("Erro ao buscar usuários:", error.message)
    }
}
buscarUsuarios(1);  // (1) - usuario com id 1

async function criarPost() {
  const novoPost = {
    title: "Meu teste",
    body: "Meu conteudo",
    userId: 1
  };
  const resposta = await fetch("https://jsonplaceholder.typicode.com/posts/",{
    method: "POST",
    headers: {"Content-Type": "application/json"},
    body: JSON.stringfy(novoPost)
  });
  const postCriado = await resposta.json();
  console.log.log("Post criado: ", postCriado)
}
criarPost();
/////////////////////////

## Aula 15 ##
//biblioteca node-localstorage
//strigfy - transforma objetos JSON em strigs / parse - deixa o bjeto manipulável/ JSON() - para receber os objetos

//then
//async, await

// async function getUsers() {
//     try{}
//     catch(err){}
// };

const { LocalStorage } = require("node-localstorage");
const localStorage = new LocalStorage("./dados");

async function carregarDados() {
	try {
		const [posts, comments, users] = await Promise.allSettled([
			fetch("https://jsonplaceholder.typicode.com/posts").then((res) =>
				res.json()
			),
			fetch("https://jsonplaceholder.typicode.com/comments").then((res) =>
				res.json()
			),
			fetch("https://jsonplaceholder.typicode.com/users").then((res) =>
				res.json()
			),
		]);
		localStorage.setItem("posts", JSON.stringify(posts)); //armazena objetos

		const postsSalvo = JSON.parse(localStorage.getItem("posts"));
		postsSalvo.forEach((post) => {
			console.log(post.title);
		});

		console.log(posts, comments, users);
	} catch (erro) {
		console.error("Erro ao carregar dados: ", erro);
	}
}
carregarDados();
_____________________________________________________________________________________
atividade: Lista de Exercícios - JavaScript Fundamentals para React

//Crie uma função que recebe um número como argumento. A função deve imprimir no console "Positivo" se o número for maior que zero, "Negativo" se for menor que zero, e "Zero" se for igual a zero.

const arrayNumeros = [-2, -1, 0, 1, 2];
function verificarNumero(numero) {
    if (numero < 0) {
      console.log("negativo")
    } else if (numero > 0){
      console.log("positivo")
    } else{
      console.log("zero")
    }
}

verificarNumero(2); 
verificarNumero(-2); 
verificarNumero(0);
console.log("\n");


//Escreva um código que use um loop for para imprimir os números de 1 a 10 no console.
for (let i = 1; i<= 10; i++){
  console.log(i);
}
console.log("\n");


//Dado um array de números, use um loop for e uma condição if para criar um novo array contendo apenas os números pares.
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const numerosPares = [];
 for (let i = 0; i< numeros. length; i++){
  if (numeros[i] %2 === 0){
    numerosPares.push(numeros[i]);
  }
 }
console.log(numerosPares);


//Dado um array de nomes, use o método forEach para imprimir cada nome no console, precedido pela saudação "Olá, ".
const nomes = ["Ana", "Bruno", "Carlos"];

nomes.forEach(nome => {
  console.log(`Olá, ${nome}`)
});
console.log("\n");


//Use o método filter para criar um novo array que contenha apenas os produtos com preço acima de R$ 500.
const produtos1 = [
    { nome: "Notebook", preco: 2500 },
    { nome: "Mouse", preco: 80 },
    { nome: "Teclado", preco: 120 },
    { nome: "Monitor", preco: 950 },
    { nome: "Cadeira", preco: 600 }
];

const produtosCaros = produtos1.filter(produto => produto.preco > 500);
console.log(produtosCaros);
console.log("\n");


//Use o método map para criar um novo array que contenha apenas os nomes dos produtos do array da questão anterior.
const produtos2 = [
    { nome: "Notebook", preco: 2500 },
    { nome: "Mouse", preco: 80 },
    { nome: "Teclado", preco: 120 },
    { nome: "Monitor", preco: 950 },
    { nome: "Cadeira", preco: 600 }
];

const nomesDosProdutos = produtos2.map(produto => produto.nome);
console.log(nomesDosProdutos); 
console.log("\n");


//Você recebeu uma string JSON com uma lista de usuários. Primeiro, converta a string JSON em um objeto JavaScript. Depois, use filter para criar um novo array contendo apenas os usuários ativos (isActive: true).
const usuariosJson1 = `[
    {"id": 1, "nome": "Alice", "isActive": true},
    {"id": 2, "nome": "Bob", "isActive": false},
    {"id": 3, "nome": "Charlie", "isActive": true}
]`;

const usuarios1 = JSON.parse(usuariosJson1);
const usuariosAtivos = usuarios1.filter(usuario => usuario.isActive);
console.log(usuariosAtivos);
console.log("\n");


//Usando a mesma string JSON da questão anterior, crie um novo array que contenha strings no formato "ID: [id], Nome: [nome]" para cada usuário.
const usuariosJson2 = `[
    {"id": 1, "nome": "Alice", "isActive": true},
    {"id": 2, "nome": "Bob", "isActive": false},
    {"id": 3, "nome": "Charlie", "isActive": true}
]`;

const usuarios2 = JSON.parse(usuariosJson2);
const infoUsuarios = usuarios2.map(usuario => `ID: ${usuario.id}, Nome: ${usuario.nome}`);
console.log(infoUsuarios);
console.log("\n");


//Dado um array de números, use o método reduce para calcular a soma total de todos os números.
const valores = [10, 20, 30, 40, 50];

const somaTotal = valores.reduce((acc,valorAtual) => acc + valorAtual, 0);
console.log(somaTotal); 
console.log("\n");


//Você tem um JSON de carrinho de compras. Sua tarefa é calcular o valor total dos itens da categoria "Eletrônicos". Para isso, você precisará:

//Converter a string JSON para um objeto.
//Filtrar (filter) os itens que são da categoria "Eletrônicos".
//Mapear (map) o array filtrado para obter um array apenas com os preços.
//Reduzir (reduce) o array de preços para obter a soma total.

const carrinhoJson = `[
    {"nome": "Smartphone", "categoria": "Eletrônicos", "preco": 1500},
    {"nome": "Tênis", "categoria": "Vestuário", "preco": 350},
    {"nome": "Fone de Ouvido", "categoria": "Eletrônicos", "preco": 250},
    {"nome": "Camiseta", "categoria": "Vestuário", "preco": 80},
    {"nome": "Smartwatch", "categoria": "Eletrônicos", "preco": 800}
]`;

const meuCarrinho = JSON.parse(carrinhoJson);

const totalValor = meuCarrinho
    .filter(item => item.categoria === "Eletrônicos")
    .map(item => item.preco)
    .reduce((acc, precoAtual) => acc + precoAtual, 0);
console.log(totalValor); 
_______________________________________________________________________________________

## Aula 16 ##

//cd src

- promise.all
- promise.race
- IIFE // (async () => {
           }) ();
  
- nullish coalescing
-------------------------------
  src> services > /postServices
                  /users
       main
       package.json


postService:
//criar uma função exportável
export async function fetchPosts () {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/posts');
      if(!response.ok) throw new Error('Erro ao buscar posts')
    return await response.json();
    } catch (error){
        console.log(error);
        return [];
    }
  }
----------

users:
//criar uma função exportável
export async function fetchUsers () {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/users');
      if(!response.ok) throw new Error('Erro ao buscar posts')
    return await response.json();
    } catch (error){
        console.log(error);
        return [];
    }
}
----------

main:
import { fetchPosts } from "./services/postService.js";
import { fetchUsers } from "./services/users.js";
import { fetchComments } from "./services/comments.js";

//usar promise.all e promise.race
async function main() {
	// const posts = await fetchPosts();
	// console.log("Total de posts: ", posts.length);
    try{
        // promise.all
        // requisições em paralelo
        const [posts, users, comments] = await Promise.all([
            fetchPosts(),
            fetchUsers(),
            fetchComments()
        ]);  

        //promise.race
        // const primeiroRes = await Promise.race([
        //     fetchPosts(),
        //     fetchUsers()
        // ]);
        // if(Array.isArray(primeiroRes)&& primeiroRes[0]?.user.id !== undefined){
        //     //fetchPosts venceu a corrida
        // }

        console.log("total de posts: ", posts.length);
        console.log("total de users: ", users.length);
        console.log("total de users: ", comments.length)

        //primero autor de um post
        //posts[0]
        const primeiroAutor = 
        users.find(user => user.id === posts[0]?.userId)?.name ?? 'Autor desconhecido' //nullish coalescing
        console.log("autor do primeiro post: ", primeiroAutor);
    }catch(error){
        console.log("erro: ", error)
    }
}
main();
------------

comments:
//criar uma função exportável
export async function fetchComments () {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/comments');
      if(!response.ok) throw new Error('Erro ao buscar posts')
    return await response.json();
    } catch (error){
        console.log(error);
        return [];
    }
  }


-----------
resultado:

total de posts:  100
total de users:  10
autor do primeiro post:  Autor desconhecido
