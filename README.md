# Instalando o cypress
   - Instalar o node.js:
           npm init -y


   - Instalar o Cypress com npm:   
           npm install cypress --save-dev
 


# Rodando os testes do cypress
- Para rodar os testes no terminar

  
       - Execução de todos os testes = **npx cypress run --browser=chrome**
       - Execução de somente uma pasta de teste = **npx cypress run --spec** + caminho da pasta.
               ex: **npx cypress run --spec "cypress/e2e/RegistroUsuário/TestPageNovoUsuário.cy.js"**


 - Para rodar os teste na página web
       - **npx cypress open**


# Cenários de testes:


- Feature: Validação de Visualização dos Produtos

  Como usuário logado
  Eu quero visualizar os produtos disponíveis
  Para que eu possa comprar os itens que desejo.

  Cenario: Sucesso ao acessar a página de produtos
    Given que eu estou logado com um e-mail válido e senha válida
    When eu clico no botão "Registrar"
    Then eu devo ser redirecionado para a página de produtos
    And a página deve exibir "Itens Disponíveis"

  Cenario: Exibição correta dos produtos
    Given que eu estou logado com um e-mail válido e senha válida
    When eu clico no botão "Registrar"
    Then os seguintes produtos devem ser visíveis:
      | Produto A - 29.99 |
      | Produto B - 49.99 |
      | Produto C - 19.99 |
      | Produto D - 99.99 |
      | Produto E - 59.99 |
  

- Feature:  Validação de Campos Obrigatórios no Registro

  
Cenário: Validação do campo E-mail no Registro
Dado que o usuário acessa a página de registro e tenta submeter o formulário sem preencher o campo de E-mail
Quando o campo de E-mail não é preenchido
Então o campo de E-mail deve ser obrigatório e exibir a mensagem de erro "Preencha este campo."


Cenário : Validação do campo Senha no Registro
Dado que o usuário preenche o campo de E-mail e tenta submeter o formulário sem preencher o campo de Senha
Quando o campo de Senha não é preenchido
Então o campo de Senha deve ser obrigatório e exibir a mensagem de erro "Preencha este campo."

Cenário : Validação do campo Confirmação de Senha no Registro
Dado que o usuário preenche os campos de E-mail e Senha e tenta submeter o formulário sem preencher o campo de Confirmação de Senha
Quando o campo de Confirmação de Senha não é preenchido
Então o campo de Confirmação de Senha deve ser obrigatório e exibir a mensagem de erro "Preencha este campo."

Cenário : Funcionamento do botão "Voltar para o Login" no Registro
Dado que o usuário acessa a página de registro
Quando ele clica no botão "Voltar para o Login"
Então ele deve ser redirecionado para a página de Login.


- Feature: Validação de Campos Obrigatórios no Login
  
Cenário : Validação do campo E-mail no Login
Dado que o usuário acessa a página de login e tenta submeter o formulário sem preencher o campo de E-mail
Quando o campo de E-mail não é preenchido
Então o campo de E-mail deve ser obrigatório e exibir a mensagem de erro "Preencha este campo."

Cenário : Validação do campo Senha no Login
Dado que o usuário preenche o campo de E-mail e tenta submeter o formulário sem preencher o campo de Senha
Quando o campo de Senha não é preenchido
Então o campo de Senha deve ser obrigatório e exibir a mensagem de erro "Preencha este campo."
