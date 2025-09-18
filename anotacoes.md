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
