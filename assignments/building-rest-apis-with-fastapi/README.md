# 📘 Tarefa: Building REST APIs with FastAPI

## 🎯 Objective

Construa uma API REST para gerenciar uma coleção de livros usando o framework FastAPI. Você praticará rotas HTTP, validação de dados e respostas apropriadas, mantendo os dados em memória para focar nos conceitos da API.

## 📝 Tasks

### 🛠️ Criar a aplicação e consultar livros

#### Descrição
Configure uma aplicação FastAPI para uma biblioteca. Crie uma rota para verificar se a API está funcionando e outra para listar livros. Use uma lista em memória com pelo menos dois livros para começar.

#### Requisitos
O programa completo deve:

- Criar uma instância FastAPI em um arquivo `main.py`
- Implementar `GET /health`, retornando um JSON que indique que a API está funcionando
- Implementar `GET /books`, retornando a lista de livros
- Representar cada livro com pelo menos `id`, `title` e `author`
- Executar a aplicação com Uvicorn e permitir que a documentação interativa seja acessada em `/docs`


### 🛠️ Validar e gerenciar livros

#### Descrição
Permita cadastrar livros e consultar um livro específico. Use modelos do Pydantic para validar os dados recebidos e retorne uma resposta adequada quando um livro não existir.

#### Requisitos
O programa completo deve:

- Definir um modelo de entrada com `title` e `author` obrigatórios e não vazios
- Implementar `POST /books` para cadastrar um livro e gerar um `id` único
- Retornar o livro criado com o status HTTP `201 Created`
- Implementar `GET /books/{book_id}` para buscar um livro pelo identificador
- Retornar o status HTTP `404 Not Found` quando o identificador não corresponder a um livro
- Implementar `PUT /books/{book_id}` para substituir os dados de um livro existente
- Usar validação do Pydantic para rejeitar dados inválidos


### 🛠️ Excluir livros e testar a API

#### Descrição
Complete as operações da API excluindo livros e teste os caminhos de sucesso e de erro usando a documentação interativa do FastAPI.

#### Requisitos
O programa completo deve:

- Implementar `DELETE /books/{book_id}` para excluir um livro existente
- Retornar o status HTTP `204 No Content` ao excluir um livro com sucesso
- Retornar `404 Not Found` ao tentar excluir um livro inexistente
- Testar as operações de listar, cadastrar, consultar, atualizar e excluir em `/docs`
- Confirmar que a lista de livros reflete as alterações feitas durante a execução
