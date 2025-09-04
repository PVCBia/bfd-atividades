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
