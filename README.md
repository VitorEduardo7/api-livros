📖 Sobre o projeto

Este repositório contém o desenvolvimento de uma API para cadastro de livros, construída passo a passo ao longo das aulas, como parte de uma avaliação prática. O objetivo é entender, na prática, como uma aplicação backend se conecta a um banco de dados relacional e expõe operações via HTTP.

O projeto é dividido em 4 etapas, entregues progressivamente:

Parte	Conteúdo
🧩 1	Preparação do ambiente, estrutura do projeto e conexão com o MySQL
➕ 2	Modelagem da tabela livros, schemas com Pydantic e rotas POST / GET
✏️ 3	Rotas PUT / DELETE, tratamento de erros e finalização do CRUD
🎨 4	Interface web (HTML, CSS e JavaScript) consumindo a API
🚀 Tecnologias utilizadas
Tecnologia	Função no projeto
Python	Linguagem principal da aplicação
FastAPI	Framework para construção da API
Uvicorn	Servidor ASGI que executa a aplicação
SQLAlchemy	ORM para comunicação com o banco de dados
PyMySQL	Driver de conexão entre Python e MySQL
Pydantic Settings	Leitura e validação das variáveis de ambiente
MySQL	Banco de dados relacional
🗂️ Estrutura do projeto
text
api-livros/
├── .env                     # Configurações locais (não versionado)
├── .gitignore
├── requirements.txt
├── database/
│   └── biblioteca_db.sql    # Estrutura/dados do banco
└── app/
    ├── __init__.py
    ├── database.py          # Conexão com o MySQL
    └── main.py               # Aplicação FastAPI
📕 Modelo de dados: Livro
Campo	Tipo	Descrição
id	inteiro	Identificador único
titulo	texto	Título do livro
autor	texto	Nome do autor
ano_publicacao	inteiro	Ano de publicação
disponivel	booleano	Indica se o livro está disponível
🔌 Rotas planejadas
Método	Rota	Descrição
POST	/livros	Cadastrar um novo livro
GET	/livros	Listar todos os livros
GET	/livros/{id}	Consultar um livro específico
PUT	/livros/{id}	Atualizar os dados de um livro
DELETE	/livros/{id}	Remover um livro
GET	/health	Verificar status da API e conexão com o banco
⚙️ Como rodar o projeto localmente
1. Clone o repositório
bash
git clone <url-do-repositorio>
cd api-livros
2. Crie e ative o ambiente virtual
bash
python -m venv .venv
.venv\Scripts\activate.bat
3. Instale as dependências
bash
pip install -r requirements.txt
4. Configure o .env

Crie um arquivo .env na raiz do projeto com base no exemplo:

dotenv
DB_USER=root
DB_PASSWORD=sua_senha
DB_HOST=localhost
DB_PORT=3306
DB_NAME=biblioteca_db
5. Importe o banco de dados

Pelo phpMyAdmin, importe o arquivo database/biblioteca_db.sql para criar o banco biblioteca_db.

6. Inicie o servidor
bash
uvicorn app.main:app --reload

A API estará disponível em: http://127.0.0.1:8000

📑 Documentação interativa

Assim que o servidor estiver rodando, a documentação gerada automaticamente pelo FastAPI pode ser acessada em:

Swagger UI: http://127.0.0.1:8000/docs
ReDoc: http://127.0.0.1:8000/redoc
🎓 Contexto acadêmico

Este projeto faz parte de uma atividade avaliativa conduzida em sala de aula, com entregas por etapas via commits no GitHub, seguindo o cronograma definido pelo professor para cada turma.
