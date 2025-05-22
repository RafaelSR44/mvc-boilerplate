# Pergunta em aula

#### Explique com suas palavras o funcionamento do models, controller, e fale sobre endpoints no projeto.

#### Resposta:

Em um projeto web estruturado no padrão MVC, os models são responsáveis por definir a estrutura das tabelas no banco de dados e suas relações. No seu caso, aluno.js, curso.js e professor.js definem as entidades principais, com destaque para o relacionamento entre alunos e cursos através de uma chave estrangeira. Os controllers (alunoController.js, cursoController.js e professorController.js) atuam como intermediários entre o usuário e os dados, processando requisições e executando operações CRUD (Criar, Ler, Atualizar e Deletar). Já os endpoints, definidos nos arquivos de rotas (alunos.js, cursos.js e professores.js), são URLs que permitem acesso às funcionalidades do sistema. Por exemplo, a rota http://localhost:3000/alunos permite gerenciar alunos e cursos, enquanto http://localhost:3000/professores gerencia dados dos professores. Quando um usuário acessa uma URL, o servidor identifica a rota correspondente, que chama o método apropriado no controller, que por sua vez utiliza o model para interagir com o banco de dados e retornar uma resposta. Esta arquitetura organiza claramente as responsabilidades, facilitando manutenção e escalabilidade do projeto.

## 🧠 Perguntas para medir aprendizado (responder neste README)

1. **Explique com suas palavras o papel de cada camada da arquitetura MVC usada neste projeto.**  
  *Como o Model, o Controller e a View interagem entre si?*

Na arquitetura MVC deste projeto:

- **Model**: Responsável pela estrutura dos dados e regras de negócio. Define como os dados são armazenados no PostgreSQL e suas relações (ex: alunos.js, cursos.js). 

- **View**: Camada de apresentação que exibe dados ao usuário através de HTML com tabelas e formulários. Recebe inputs e mostra outputs de forma organizada.

- **Controller**: Intermediário que processa requisições, conectando Model e View. Recebe solicitações das rotas, manipula dados via Model e retorna respostas apropriadas (ex: alunoController.js).

A interação ocorre quando uma requisição chega a uma rota, que aciona o Controller apropriado. O Controller consulta o Model para acessar/modificar dados e retorna resultados para a View exibir ao usuário.

2. **Como ocorre o envio e o recebimento de dados no formato JSON neste projeto?**  
  *Cite uma rota que responde em JSON e explique seu funcionamento.*

O envio e recebimento de dados em JSON ocorre através das requisições HTTP entre cliente e servidor. Por exemplo, a rota GET `/alunos/json` retorna uma lista de alunos em formato JSON:

```javascript
router.get('/alunos/json', async (req, res) => {
   const alunos = await Aluno.findAll();
   res.json(alunos);
});
```

Quando acessada, esta rota:
1. Busca todos os alunos no banco através do model
2. Converte automaticamente os dados para JSON usando `res.json()`
3. Retorna ao cliente com Content-Type: application/json

O cliente pode então processar essa resposta JSON para exibir ou manipular os dados como necessário.

3. **Qual a importância de usar HTML básico com formulários e tabelas para organizar e manipular dados no navegador?**  
  *Por que esse tipo de estrutura ainda é útil em projetos back-end com Node.js?*

O HTML básico com formulários e tabelas continua sendo fundamental por:

1. **Simplicidade e Consistência:**
  - Funciona em qualquer navegador sem dependências
  - Interface previsível e familiar aos usuários
  - Menor curva de aprendizado para desenvolvedores

2. **Funcionalidade Nativa:**
  - Validação de campos integrada
  - Submissão de dados padronizada
  - Organização tabular eficiente dos dados

3. **Integração com Backend:**
  - Comunicação direta com rotas Node.js
  - Processamento de formulários simplificado
  - Renderização rápida do lado do servidor

Mesmo com frameworks modernos, HTML básico oferece uma base sólida para prototipar e testar funcionalidades backend, especialmente em projetos focados em lógica de servidor com Node.js.



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