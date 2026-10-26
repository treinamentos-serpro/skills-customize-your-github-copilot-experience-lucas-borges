# 📘 Atividade: Persistência de Dados com FastAPI e SQLite

## 🎯 Objective

Evolua a API de livros criada com FastAPI para armazenar dados em um banco SQLite usando SQLAlchemy. Ao final, as operações CRUD devem usar o banco de dados e os livros cadastrados devem continuar disponíveis após reiniciar a aplicação.

## 📝 Tasks

### 🛠️ Configurar o banco de dados e o modelo de livro

#### Descrição
Configure uma conexão com um arquivo SQLite e defina o modelo de banco de dados que representará os livros. Reaproveite a estrutura da API FastAPI de livros da atividade anterior.

#### Requisitos
O programa completo deve:

- Configurar SQLAlchemy para conectar a API a um arquivo SQLite local
- Definir uma tabela `books` com `id` como chave primária e campos `title` e `author`
- Criar uma sessão de banco de dados para uso pelas rotas
- Criar a tabela automaticamente quando a aplicação iniciar, sem exigir uma ferramenta de migrações
- Manter os modelos Pydantic usados para validar as requisições separados do modelo SQLAlchemy usado para persistência


### 🛠️ Persistir cadastro e consulta de livros

#### Descrição
Substitua a lista em memória por operações no banco de dados para cadastrar livros e consultar a coleção ou um livro específico.

#### Requisitos
O programa completo deve:

- Adaptar `GET /books` para retornar os livros armazenados no SQLite
- Adaptar `POST /books` para salvar um livro no SQLite e retornar o livro criado com status HTTP `201 Created`
- Adaptar `GET /books/{book_id}` para buscar um livro pelo identificador
- Retornar status HTTP `404 Not Found` quando o livro solicitado não existir
- Fechar ou liberar a sessão do banco de dados ao final de cada requisição, inclusive quando ocorrer um erro


### 🛠️ Completar o CRUD e verificar a persistência

#### Descrição
Migre as operações de atualização e exclusão para o banco de dados e verifique que os registros não desaparecem quando a API é reiniciada.

#### Requisitos
O programa completo deve:

- Adaptar `PUT /books/{book_id}` para atualizar um livro existente no SQLite
- Adaptar `DELETE /books/{book_id}` para remover um livro existente e retornar status HTTP `204 No Content`
- Retornar status HTTP `404 Not Found` ao atualizar ou excluir um livro inexistente
- Testar as operações de listar, cadastrar, consultar, atualizar e excluir em `/docs`
- Cadastrar um livro, reiniciar a aplicação e confirmar que o livro continua disponível
- Confirmar que a coleção retornada pela API reflete as alterações feitas no banco de dados
