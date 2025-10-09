# Aula20 #
//Lista de produtos

import ProductCard from "./ProductCard";

function ProductList() {
    const products = [
        {   
            id:1,
            name: "notebook", 
            price: 4000,
            image: "https://placeholder.co/200x150?text=Notebook"
        },
        {
            id:2,
            name: "smatphone", 
            price: 3000,
            image: "https://placeholder.co/200x150?text=Smartphone"
        }
    ];

    return (
        <>
            {products.map(product => (
                <ProductCard 
                    id={product.id}
                    name={product.name}
                    price={product.price}
                    image={product.image} />
            ))}
        </>
    )
}

export default ProductList;
--------------
//crie um componente `ProductCard` que receba via props
// - `name` (nome do produto)
// - `price` (preço)
// - `image` (URL da imagem)
// e use dentro de um `ProductList` para enderizar varios produtos

function ProductCard ({name, price, image}) {
  return(
    <>
        <h2>{name}</h2>
        <h3>R$ {price}</h3>
        <img src={image} alt={name} />
    </>
  );
}

export default ProductCard;
--------------------
import './App.css'
import ProductList from './components/ProductList';

function App() {

    return (
    <>
      <ProductList/>
    </>
  )
}

export default App;
