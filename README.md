![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.110-009688?style=flat-square&logo=fastapi&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-F5A623?style=flat-square)

# API de Livros

Projeto de uma API para cadastro e consulta de livros, desenvolvida ao longo das aulas como parte de uma avaliação prática. A ideia por trás dela é simples: entender, na prática, como uma aplicação backend conversa com um banco de dados relacional e expõe suas operações através de HTTP.

O projeto foi construído em quatro etapas, cada uma entregue ao final da respectiva aula.

| Etapa | O que foi feito |
| --- | --- |
| 1 | Preparação do ambiente, estrutura inicial do projeto e conexão com o MySQL |
| 2 | Modelagem da tabela `livros`, validação com Pydantic e rotas `POST` / `GET` |
| 3 | Rotas `PUT` / `DELETE`, tratamento de erros e fechamento do CRUD |
| 4 | Interface web (HTML, CSS e JavaScript) consumindo a API |

---

## Tecnologias

| Tecnologia | Onde entra no projeto |
| --- | --- |
| Python | Linguagem usada na aplicação |
| FastAPI | Framework da API |
| Uvicorn | Servidor que roda a aplicação |
| SQLAlchemy | ORM usado para falar com o banco |
| PyMySQL | Driver de conexão com o MySQL |
| Pydantic Settings | Leitura das variáveis do `.env` |
| MySQL | Banco de dados relacional |

---

## Estrutura do projeto

```
api-livros/
├── .env                     # configurações locais, não vai para o GitHub
├── .gitignore
├── requirements.txt
├── database/
│   └── biblioteca_db.sql    # estrutura e dados do banco
└── app/
    ├── __init__.py
    ├── database.py          # conexão com o MySQL
    └── main.py              # aplicação FastAPI
```

---

## Modelo de dados: Livro

| Campo | Tipo | Descrição |
| --- | --- | --- |
| `id` | inteiro | identificador único, gerado pelo banco |
| `titulo` | texto | título do livro |
| `autor` | texto | nome do autor |
| `ano_publicacao` | inteiro | ano em que o livro foi publicado |
| `disponivel` | booleano | indica se o livro está disponível para empréstimo |

---

## Rotas da API

| Método | Rota | O que faz |
| --- | --- | --- |
| `POST` | `/livros` | cadastra um livro novo |
| `GET` | `/livros` | lista todos os livros |
| `GET` | `/livros/{id}` | busca um livro específico |
| `PUT` | `/livros/{id}` | atualiza os dados de um livro |
| `DELETE` | `/livros/{id}` | remove um livro |
| `GET` | `/health` | verifica se a API e o banco estão respondendo |

---

## Rodando o projeto localmente

**1. Clone o repositório**

```bash
git clone <url-do-repositorio>
cd api-livros
```

**2. Crie e ative o ambiente virtual**

```bash
python -m venv .venv
.venv\Scripts\activate.bat
```

**3. Instale as dependências**

```bash
pip install -r requirements.txt
```

**4. Configure o `.env`**

Crie um arquivo `.env` na raiz do projeto com os dados do seu MySQL local:

```dotenv
DB_USER=root
DB_PASSWORD=sua_senha
DB_HOST=localhost
DB_PORT=3306
DB_NAME=biblioteca_db
```

**5. Importe o banco de dados**

Pelo phpMyAdmin, importe o arquivo `database/biblioteca_db.sql` para criar o banco `biblioteca_db` com a estrutura e os dados já cadastrados.

**6. Inicie o servidor**

```bash
uvicorn app.main:app --reload
```

A API sobe em `http://127.0.0.1:8000`.

---

## Documentação interativa

Com o servidor rodando, o próprio FastAPI gera a documentação da API:

- Swagger UI: `http://127.0.0.1:8000/docs`
- ReDoc: `http://127.0.0.1:8000/redoc`

---

## Sobre a entrega

Este é um projeto acadêmico, desenvolvido em sala de aula e entregue por etapas, com um commit no GitHub ao final de cada uma, seguindo o cronograma definido para a turma.
