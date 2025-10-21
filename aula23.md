src/ components/ Layout.jsx
import {Link, Outlet} from "react-router-dom";

function Layout(){
 return(
    <>
    {/*nav (Link to= ) - hr/ - main - footer*/}
    <nav>
        <Link to= "/">Usuários</Link> | {" "}
        <Link to= "/produtos">Produtos</Link>
    </nav>
    <hr/>
    <main>
        <Outlet/>
    </main>
    <footer>
        
    </footer>

    </>
 )
    
}
export default Layout;
------------------------
src/ components/ Login.jsx
function Login(){
    return (
        <div>
            <h1>Login</h1>
            <p>Faça login para acessar</p>
        </div>
    )
}
export default Login;
----------------------
src/ components/ PrivateRoute.jsx
import {Navigate, Outlet} from 'react-router-dom'

const useAuth = () => {
    const userIsloggesdIn = true;
    return userIsloggesdIn;
}

function PrivateRoute(){
    const isAuth = useAuth();
    return isAuth ? <Outlet/> : <Navigate to= "/login"/>
}

export default PrivateRoute;
------------------------
src/App.jsx
import './App.css';
import Login from '../../src/components/Login';
import PrivateRoute from '../../src/components/PrivateRoute';
import Usuarios from './pages/Usuários';
import Layout from '../../src/components/Layout';

const router = createBrowserRouter(
  createRoutesFromElements(
    <>
      <BrouserRouter>
      <Routes>

        <Route path="/login" element= {<Login/>}>

        <Route path="/" element={<Layout/>} />
          <Route index element={<Usuarios />} />
        </Route>

        <Route element= {<PrivateRoute/>}>
          <Route path="/produtos" element={<Produtos/>} />
        </Route>

      </Routes>
      </BrouserRouter>

    </>
  )
);

function App() {
  return <RouterProvider router={router}/>
}

export default App
-------------------------
