## Aula 19 ##

import React, { useState, useEffect } from 'react';
import { Plus, Minus, Eye, EyeOff, X, RotateCw, Loader, Clock, Search, Send, Check } from 'lucide-react';

// URL sugerida para o exercício 8
const API_URL = "https://jsonplaceholder.typicode.com/todos/1";
const CORES = ['#ef4444', '#3b82f6', '#10b981', '#f59e0b', '#8b5cf6']; // Vermelho, Azul, Verde, Amarelo, Roxo

// Utilitário de componente para encapsular cada exercício
const Card = ({ title, children }) => (
    <div className="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow border border-gray-100 flex flex-col h-full">
        <h3 className="text-xl font-semibold text-gray-800 mb-4 border-b pb-2">{title}</h3>
        <div className="flex-grow flex items-start justify-center p-2">
            {children}
        </div>
    </div>
);

// 1. Contador Simples (useState)
const ContadorSimples = () => {
    const [contador, setContador] = useState(0);

    return (
        <div className="flex flex-col items-center space-y-4">
            <p className="text-5xl font-extrabold text-blue-600">{contador}</p>
            <div className="flex space-x-3">
                <button
                    onClick={() => setContador(prev => prev + 1)}
                    className="flex items-center bg-green-500 hover:bg-green-600 text-white font-bold py-2 px-4 rounded-lg shadow-md transition-all active:scale-95"
                >
                    <Plus className="w-5 h-5 mr-1" /> Incrementar
                </button>
                <button
                    onClick={() => setContador(prev => prev - 1)}
                    className="flex items-center bg-red-500 hover:bg-red-600 text-white font-bold py-2 px-4 rounded-lg shadow-md transition-all active:scale-95"
                >
                    <Minus className="w-5 h-5 mr-1" /> Decrementar
                </button>
            </div>
        </div>
    );
};

// 2. Exibir/Esconder Texto (useState booleano)
const ExibirEsconderTexto = () => {
    const [visivel, setVisivel] = useState(true);

    return (
        <div className="flex flex-col items-center space-y-4 w-full">
            <button
                onClick={() => setVisivel(!visivel)}
                className="flex items-center w-full justify-center bg-purple-500 hover:bg-purple-600 text-white font-bold py-2 px-4 rounded-lg shadow-md transition-all active:scale-[0.98]"
            >
                {visivel ? <EyeOff className="w-5 h-5 mr-2" /> : <Eye className="w-5 h-5 mr-2" />}
                {visivel ? 'Esconder Texto' : 'Mostrar Texto'}
            </button>
            {visivel && (
                <p className="text-center p-3 border-l-4 border-purple-500 bg-purple-50 text-gray-700 w-full transition-opacity duration-300">
                    Este texto está visível.
                </p>
            )}
        </div>
    );
};

// 3. Input Controlado (useState para string e Limpar)
const InputControlado = () => {
    const [texto, setTexto] = useState('');

    const handleChange = (event) => {
        setTexto(event.target.value);
    };

    const handleLimpar = () => {
        setTexto('');
    };

    return (
        <div className="flex flex-col w-full space-y-3">
            <input
                type="text"
                value={texto}
                onChange={handleChange}
                placeholder="Digite algo aqui..."
                className="p-3 border-2 border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 transition-colors w-full"
            />
            <button
                onClick={handleLimpar}
                disabled={!texto}
                className="flex items-center justify-center bg-yellow-500 hover:bg-yellow-600 text-white font-bold py-2 px-4 rounded-lg shadow-md transition-all active:scale-[0.98] disabled:opacity-50"
            >
                <X className="w-5 h-5 mr-2" /> Limpar Input
            </button>
            <p className="mt-2 text-gray-700 break-words">
                Você está digitando: <span className="font-mono text-blue-700">{texto || '...'}</span>
            </p>
        </div>
    );
};

// 4. Mudança de Cor de Fundo (useState para índice)
const MudancaCorFundo = () => {
    const [corIndex, setCorIndex] = useState(0);

    const mudarCor = () => {
        // Incrementa o índice e usa o operador módulo (%) para voltar a 0 quando atingir o final do array.
        setCorIndex((prevIndex) => (prevIndex + 1) % CORES.length);
    };

    const corAtual = CORES[corIndex];

    return (
        <div className="flex flex-col items-center space-y-4 w-full">
            <div
                style={{ backgroundColor: corAtual }}
                className="w-full h-20 rounded-lg shadow-inner transition-colors duration-500 flex items-center justify-center text-white text-lg font-bold"
            >
                Cor Atual
            </div>
            <button
                onClick={mudarCor}
                style={{ backgroundColor: corAtual }}
                className="flex items-center justify-center text-white font-bold py-2 px-4 rounded-lg shadow-md transition-all active:scale-[0.98] duration-500 w-full"
            >
                <RotateCw className="w-5 h-5 mr-2" /> Mudar Cor
            </button>
        </div>
    );
};

// 5 & 6. Lista de Tarefas (Adicionar e Remover)
const ListaTarefas = () => {
    const [tarefas, setTarefas] = useState(['Estudar React', 'Fazer exercícios', 'Comprar café']);
    const [novaTarefa, setNovaTarefa] = useState('');

    const handleAdicionar = (e) => {
        e.preventDefault();
        if (novaTarefa.trim() === '') return;

        // 5. Adicionar: Cria um novo array com a nova tarefa no final.
        setTarefas([...tarefas, novaTarefa.trim()]);
        setNovaTarefa('');
    };

    const handleRemover = (indiceParaRemover) => {
        // 6. Remover: Usa filter() para criar um novo array sem o item com o índice correspondente.
        const novoArray = tarefas.filter((_, index) => index !== indiceParaRemover);
        setTarefas(novoArray);
    };

    return (
        <div className="w-full flex flex-col space-y-4">
            <form onSubmit={handleAdicionar} className="flex space-x-2">
                <input
                    type="text"
                    value={novaTarefa}
                    onChange={(e) => setNovaTarefa(e.target.value)}
                    placeholder="Nova tarefa..."
                    className="flex-grow p-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500"
                />
                <button
                    type="submit"
                    className="bg-indigo-600 hover:bg-indigo-700 text-white p-2 rounded-lg transition-colors shadow-md active:scale-95"
                >
                    <Plus className="w-5 h-5" />
                </button>
            </form>

            <ul className="space-y-2">
                {tarefas.map((tarefa, index) => (
                    <li
                        key={index}
                        className="flex justify-between items-center bg-gray-50 p-3 rounded-lg border border-gray-200"
                    >
                        <span className="text-gray-800 flex items-center">
                            <Check className="w-4 h-4 mr-2 text-green-500"/>
                            {tarefa}
                        </span>
                        <button
                            onClick={() => handleRemover(index)}
                            className="text-red-500 hover:text-red-700 transition-colors p-1 rounded-full bg-red-100 hover:bg-red-200"
                            title="Remover"
                        >
                            <X className="w-4 h-4" />
                        </button>
                    </li>
                ))}
            </ul>
        </div>
    );
};

// 7. Monitor de Largura da Janela (useState, useEffect com Cleanup)
const MonitorLarguraJanela = () => {
    const [largura, setLargura] = useState(window.innerWidth);

    useEffect(() => {
        // Função que atualiza o estado com a nova largura
        const handleResize = () => {
            setLargura(window.innerWidth);
        };

        // Adiciona o listener quando o componente é montado
        window.addEventListener('resize', handleResize);

        // Função de limpeza (cleanup)
        // Remove o listener quando o componente é desmontado
        return () => {
            window.removeEventListener('resize', handleResize);
        };
    }, []); // Array de dependência vazio: executa apenas na montagem e desmontagem

    return (
        <div className="flex flex-col items-center space-y-2">
            <p className="text-3xl font-extrabold text-teal-600">{largura}px</p>
            <p className="text-gray-500 text-sm">(Redimensione a janela do navegador)</p>
        </div>
    );
};

// 8. Busca de Dados de API (useState, useEffect com Fetch)
const BuscaDadosAPI = () => {
    const [todo, setTodo] = useState(null);
    const [loading, setLoading] = useState(true);
    const [error, setError] = useState(null);

    useEffect(() => {
        const fetchTodo = async () => {
            try {
                const response = await fetch(API_URL);
                if (!response.ok) {
                    throw new Error(`Erro HTTP: ${response.status}`);
                }
                const json = await response.json();
                setTodo(json);
            } catch (err) {
                setError(err.message);
            } finally {
                // Remove o estado de loading após a tentativa (sucesso ou falha)
                setLoading(false);
            }
        };

        fetchTodo();
    }, []); // Array de dependência vazio: executa uma vez na montagem

    if (loading) {
        return (
            <div className="flex items-center text-blue-500 text-lg">
                <Loader className="w-6 h-6 mr-2 animate-spin" /> Carregando dados...
            </div>
        );
    }

    if (error) {
        return <p className="text-red-500 text-lg">Erro ao carregar: {error}</p>;
    }
    
    // Dados exibidos após o carregamento
    return (
        <div className="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-500 w-full shadow-inner">
            <h4 className="font-semibold text-gray-700 text-sm">Dados da API (TODO ID: {todo?.id})</h4>
            <p className="text-lg font-medium text-gray-800 mt-1">{todo?.title}</p>
            <p className={`text-sm mt-1 font-bold ${todo?.completed ? 'text-green-600' : 'text-red-600'}`}>
                Status: {todo?.completed ? 'Completa' : 'Pendente'}
            </p>
        </div>
    );
};

// 9. Relógio Digital (useState, useEffect com setInterval)
const RelogioDigital = () => {
    const [hora, setHora] = useState(new Date());

    useEffect(() => {
        // Configura o intervalo para atualizar a hora a cada 1000ms (1 segundo)
        const intervalId = setInterval(() => {
            setHora(new Date());
        }, 1000);

        // Função de limpeza: IMPORTANTE para evitar vazamento de memória
        // O setInterval será parado quando o componente for desmontado
        return () => {
            clearInterval(intervalId);
        };
    }, []); // Array de dependência vazio: executa o efeito uma vez

    // Formata a hora no padrão HH:MM:SS
    const horaFormatada = hora.toLocaleTimeString('pt-BR', {
        hour: '2-digit',
        minute: '2-digit',
        second: '2-digit',
    });

    return (
        <div className="flex items-center space-x-2">
            <Clock className="w-8 h-8 text-indigo-600" />
            <p className="text-4xl font-mono font-bold text-indigo-700">{horaFormatada}</p>
        </div>
    );
};

// 10. Filtro de Lista em Tempo Real (useState, useEffect para filtro)
const FiltroListaTempoReal = () => {
    const listaOriginal = ['Maçã', 'Banana', 'Laranja', 'Uva', 'Manga', 'Melancia', 'Abacaxi', 'Pêra'];
    const [searchText, setSearchText] = useState('');
    const [filteredList, setFilteredList] = useState(listaOriginal);

    // O useEffect é acionado sempre que 'searchText' muda.
    useEffect(() => {
        const termo = searchText.toLowerCase().trim();
        
        // Se o termo de busca estiver vazio, mostra a lista completa.
        if (termo === '') {
            setFilteredList(listaOriginal);
            return;
        }

        // Filtra a lista original
        const novaLista = listaOriginal.filter(item =>
            item.toLowerCase().includes(termo)
        );
        
        setFilteredList(novaLista);
    }, [searchText]); // Dependência: executa quando o texto de busca for alterado

    return (
        <div className="w-full flex flex-col space-y-4">
            <div className="relative">
                <input
                    type="text"
                    value={searchText}
                    onChange={(e) => setSearchText(e.target.value)}
                    placeholder="Buscar frutas..."
                    className="w-full p-3 pl-10 border-2 border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 transition-colors"
                />
                <Search className="absolute left-3 top-1/2 transform -translate-y-1/2 w-5 h-5 text-gray-400" />
            </div>
            
            <div className="max-h-60 overflow-y-auto p-2 bg-gray-50 rounded-lg border border-gray-200">
                {filteredList.length > 0 ? (
                    <ul className="space-y-1">
                        {filteredList.map((item, index) => (
                            <li key={index} className="p-2 bg-white rounded shadow-sm hover:bg-green-50 transition-colors text-gray-700">
                                {item}
                            </li>
                        ))}
                    </ul>
                ) : (
                    <p className="text-center text-gray-500 py-4">Nenhum item encontrado.</p>
                )}
            </div>
        </div>
    );
};


const App = () => {
    return (
        <div className="min-h-screen bg-gray-100 p-4 sm:p-8 font-sans">
            <h1 className="text-4xl font-extrabold text-center text-gray-900 mb-8 sm:mb-12">
                Lista de Exercícios React Hooks
            </h1>

            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
                <Card title="1. Contador Simples (useState)">
                    <ContadorSimples />
                </Card>
                <Card title="2. Exibir/Esconder (useState)">
                    <ExibirEsconderTexto />
                </Card>
                <Card title="3. Input Controlado (useState)">
                    <InputControlado />
                </Card>
                <Card title="4. Mudança de Cor (useState)">
                    <MudancaCorFundo />
                </Card>
                <Card title="5 & 6. Lista de Tarefas (Adicionar/Remover)">
                    <ListaTarefas />
                </Card>
                <Card title="7. Monitor de Largura (useEffect)">
                    <MonitorLarguraJanela />
                </Card>
                <Card title="8. Busca de Dados (useEffect + Fetch)">
                    <BuscaDadosAPI />
                </Card>
                <Card title="9. Relógio Digital (useEffect + setInterval)">
                    <RelogioDigital />
                </Card>
                <Card title="10. Filtro em Tempo Real (useEffect + Filter)">
                    <FiltroListaTempoReal />
                </Card>
                <Card title="11. Combinação de Filter e Map">
                    {/* Exemplo extra para demonstrar a combinação de métodos de array */}
                    <p className="text-center text-gray-600">
                        Combinação: Encontra os números pares do array [1, 2, 3, 4] e os dobra.
                    </p>
                    <div className="text-3xl font-bold text-pink-600 mt-4">
                        {
                            [1, 2, 3, 4, 5, 6]
                                .filter(n => n % 2 === 0) // Resultado: [2, 4, 6]
                                .map(n => n * 2)         // Resultado: [4, 8, 12]
                                .join(', ')
                        }
                    </div>
                </Card>
            </div>
        </div>
    );
};

export default App;
