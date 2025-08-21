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
