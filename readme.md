# Pergunta em aula

#### Explique com suas palavras o funcionamento do models, controller, e fale sobre endpoints no projeto.

#### Resposta:

Em um projeto web estruturado no padrão MVC, os models são responsáveis por definir a estrutura das tabelas no banco de dados e suas relações. No seu caso, aluno.js, curso.js e professor.js definem as entidades principais, com destaque para o relacionamento entre alunos e cursos através de uma chave estrangeira. Os controllers (alunoController.js, cursoController.js e professorController.js) atuam como intermediários entre o usuário e os dados, processando requisições e executando operações CRUD (Criar, Ler, Atualizar e Deletar). Já os endpoints, definidos nos arquivos de rotas (alunos.js, cursos.js e professores.js), são URLs que permitem acesso às funcionalidades do sistema. Por exemplo, a rota http://localhost:3000/alunos permite gerenciar alunos e cursos, enquanto http://localhost:3000/professores gerencia dados dos professores. Quando um usuário acessa uma URL, o servidor identifica a rota correspondente, que chama o método apropriado no controller, que por sua vez utiliza o model para interagir com o banco de dados e retornar uma resposta. Esta arquitetura organiza claramente as responsabilidades, facilitando manutenção e escalabilidade do projeto.



# Boilerplate MVC em Node.js com PostgreSQL

Este projeto é um boilerplate básico para uma aplicação Node.js seguindo o padrão MVC (Model-View-Controller), utilizando PostgreSQL como banco de dados.

## Requisitos

- Node.js (versão X.X.X)
- PostgreSQL (versão X.X.X)

## Instalação

1. **Clonar o repositório:**

```bash
   git clone https://github.com/seu-usuario/seu-projeto.git
   cd seu-projeto
```

2. **Instalar as dependências:**
    
```bash
npm install
```
    
3. **Configurar o arquivo `.env`:**
    
Renomeie o arquivo `.env.example` para `.env` e configure as variáveis de ambiente necessárias, como as configurações do banco de dados PostgreSQL.
    

Configuração do Banco de Dados
------------------------------

1. **Criar banco de dados:**
    
    Crie um banco de dados PostgreSQL com o nome especificado no seu arquivo `.env`.
    
2. **Executar o script SQL de inicialização:**
    
```bash
npm run init-db
```
    
Isso criará a tabela `users` no seu banco de dados PostgreSQL com UUID como chave primária e inserirá alguns registros de exemplo.
    

Funcionalidades
---------------

* **Padrão MVC:** Estrutura organizada em Model, View e Controller.
* **PostgreSQL:** Banco de dados relacional utilizado para persistência dos dados.
* **UUID:** Utilização de UUID como chave primária na tabela `users`.
* **Scripts com `nodemon`:** Utilização do `nodemon` para reiniciar automaticamente o servidor após alterações no código.
* **Testes:** Inclui estrutura básica para testes automatizados.

Scripts Disponíveis
-------------------

* `npm start`: Inicia o servidor Node.js.
* `npm run dev`: Inicia o servidor com `nodemon`, reiniciando automaticamente após alterações no código.
* `npm run test`: Executa os testes automatizados.
* `npm run test:coverage`: Executa os testes e gera um relatório de cobertura de código.

Estrutura de Diretórios
-----------------------

* **`config/`**: Configurações do banco de dados e outras configurações do projeto.
* **`controllers/`**: Controladores da aplicação (lógica de negócio).
* **`models/`**: Modelos da aplicação (definições de dados e interações com o banco de dados).
* **`routes/`**: Rotas da aplicação.
* **`tests/`**: Testes automatizados.
* **`views/`**: Views da aplicação (se aplicável).

Contribuição
------------

Contribuições são bem-vindas! Sinta-se à vontade para abrir um issue ou enviar um pull request.

Licença
-------

Este projeto está licenciado sob a Licença MIT.

Este README.md fornece uma visão geral clara do boilerplate, incluindo instruções de instalação, configuração do banco de dados, funcionalidades principais, scripts disponíveis, estrutura de diretórios, como contribuir e informações de licença. Certifique-se de personalizar as seções com detalhes específicos do seu projeto conforme necessário.