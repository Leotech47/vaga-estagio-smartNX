### 🔧 **Principais funções do Cypress**

Cypress é uma ferramenta de teste end-to-end (E2E) moderna focada em aplicações web. Suas funções principais incluem:

* **Teste de interface do usuário (UI)**: simula ações reais do usuário no navegador.
* **Teste de API**: envia requisições e valida respostas diretamente.
* **Verificação de DOM e estados da aplicação**.
* **Depuração em tempo real com recarregamento automático**.
* **Captura de screenshots e vídeos dos testes**.
* **Execução contínua em pipelines CI/CD.**

---

### 🚀 **Como utilizar o Cypress (passo a passo)**

#### 1. **Instalação**

Você precisa de Node.js instalado. Depois, use o npm ou yarn:

```bash
npm install cypress --save-dev
```

Para abrir o Cypress:

```bash
npx cypress open
```

Isso inicia a interface gráfica (GUI) do Cypress.

---

#### 2. **Estrutura de Diretórios**

Após a abertura, o Cypress cria automaticamente a pasta `cypress/` com subpastas como:

* `integration/` – onde os testes ficam.
* `fixtures/` – arquivos simulados (dados mock).
* `support/` – configurações globais.

---

#### 3. **Criando um teste simples**

Dentro de `cypress/e2e/`, crie um arquivo de teste:

```js
describe('Página de login', () => {
  it('Deve fazer login com sucesso', () => {
    cy.visit('https://exemplo.com/login');
    cy.get('input[name=email]').type('usuario@teste.com');
    cy.get('input[name=senha]').type('senha123');
    cy.get('button[type=submit]').click();
    cy.url().should('include', '/dashboard');
  });
});
```

---

#### 4. **Rodando testes**

* GUI: `npx cypress open` → selecione o teste.
* CLI (modo headless):

  ```bash
  npx cypress run
  ```

---

#### 5. **Boas práticas**

* Use comandos customizados para evitar repetição (`cypress/support/commands.js`).
* Use `beforeEach()` para lógica comum a vários testes.
* Separe testes por funcionalidades.

---

Aqui está um exemplo completo e básico de um projeto Cypress para testar uma página de login.

---

### 📁 Estrutura do projeto

```
meu-projeto-cypress/
├── cypress/
│   ├── e2e/
│   │   └── login.cy.js
│   ├── fixtures/
│   │   └── usuario.json
│   └── support/
│       └── commands.js
├── cypress.config.js
├── package.json
```

---

### 📦 `package.json` (com Cypress)

```json
{
  "name": "meu-projeto-cypress",
  "version": "1.0.0",
  "devDependencies": {
    "cypress": "^12.0.0"
  },
  "scripts": {
    "test": "cypress open",
    "test:run": "cypress run"
  }
}
```

Instale com:

```bash
npm install
```

---

### 🔧 `cypress.config.js`

```js
const { defineConfig } = require("cypress");

module.exports = defineConfig({
  e2e: {
    baseUrl: "http://localhost:3000",
    supportFile: "cypress/support/commands.js"
  }
});
```

---

### 📄 `cypress/e2e/login.cy.js`

```js
describe('Login', () => {
  beforeEach(() => {
    cy.visit('/login');
  });

  it('Deve logar com sucesso', () => {
    cy.fixture('usuario').then((usuario) => {
      cy.get('[name=email]').type(usuario.email);
      cy.get('[name=senha]').type(usuario.senha);
      cy.get('[type=submit]').click();
      cy.url().should('include', '/dashboard');
    });
  });

  it('Deve mostrar erro com credenciais inválidas', () => {
    cy.get('[name=email]').type('email@invalido.com');
    cy.get('[name=senha]').type('errado');
    cy.get('[type=submit]').click();
    cy.contains('Credenciais inválidas').should('be.visible');
  });
});
```

---

### 🧪 `cypress/fixtures/usuario.json`

```json
{
  "email": "teste@dominio.com",
  "senha": "123456"
}
```

---

### ✅ Comando para executar:

```bash
npx cypress open
```

---

### Pasta zipada com arquivos de teste do cypress:
https://drive.google.com/file/d/1Fhz3OgxHGZRKgw04xt2Eh94aXw8Y_hHf/view?usp=sharing

Aqui está um **exemplo concreto de caso de teste** com Cypress para um **formulário de contato** em uma aplicação web fictícia. O cenário cobre um envio bem-sucedido do formulário.

---

### 🧪 Cenário: Envio bem-sucedido do formulário de contato

#### ✅ Requisitos:

* A URL do formulário é: `https://exemplo.com/contato`
* Os campos obrigatórios:

  * Nome (`input[name=nome]`)
  * Email (`input[name=email]`)
  * Mensagem (`textarea[name=mensagem]`)
* Botão de envio: `button[type=submit]`
* Ao enviar corretamente, uma mensagem de confirmação: `"Mensagem enviada com sucesso!"` aparece.

---

### 📄 `cypress/e2e/contato.cy.js`

```js
describe('Formulário de Contato', () => {
  beforeEach(() => {
    cy.visit('https://exemplo.com/contato');
  });

  it('Deve enviar a mensagem com sucesso', () => {
    cy.get('input[name=nome]').type('João da Silva');
    cy.get('input[name=email]').type('joao@teste.com');
    cy.get('textarea[name=mensagem]').type('Olá, gostaria de mais informações.');

    cy.get('button[type=submit]').click();

    cy.contains('Mensagem enviada com sucesso!').should('be.visible');
  });
});
```

---

### 🛠️ Explicação

* `cy.visit(...)`: acessa a página de contato.
* `cy.get(...).type(...)`: preenche os campos.
* `cy.get(...).click()`: clica no botão de envio.
* `cy.contains(...).should(...)`: verifica se a confirmação aparece.

---

### Pasta zipada com o teste do projeto Cypress completo:
https://drive.google.com/file/d/18jSYUph1qxpQwGiqZzeCHWrqInLPX6_p/view?usp=sharing

Aqui está um exemplo completo de teste com Cypress que cobre:

1. **Teste de Interface do Usuário (UI)**
2. **Teste de API**
3. **Verificação de DOM e estados da aplicação**
4. **Depuração em tempo real com recarregamento automático**
5. **Captura de screenshots e vídeos**
6. **Execução contínua (CI/CD)**

---

### 📄 Exemplo: Aplicação de lista de tarefas (To-Do List)

#### Funcionalidades:

* A página exibe uma lista de tarefas.
* O usuário pode adicionar uma nova tarefa.
* A aplicação consome uma API para salvar a tarefa.
* Tarefas salvas aparecem na lista (verificação de DOM).

---

### 📁 `cypress/e2e/todo.cy.js`

```js
describe('To-Do List - Funcionalidades completas', () => {
  beforeEach(() => {
    // 1. UI: Acessa a página inicial
    cy.visit('/');
  });

  it('Deve adicionar uma nova tarefa com sucesso', () => {
    const novaTarefa = 'Estudar Cypress';

    // 2. UI: Simula digitação e clique
    cy.get('input[name=tarefa]').type(novaTarefa);
    cy.get('button#adicionar-tarefa').click();

    // 3. DOM: Verifica se a tarefa aparece na lista
    cy.get('.lista-tarefas').should('contain', novaTarefa);
  });

  it('Deve testar diretamente a API de criação de tarefas', () => {
    // 4. API: Envia requisição POST e valida resposta
    cy.request('POST', '/api/tarefas', {
      descricao: 'Tarefa via API',
      feita: false
    }).then((res) => {
      expect(res.status).to.eq(201);
      expect(res.body).to.have.property('descricao', 'Tarefa via API');
    });
  });
});
```

---

### 📸 **Captura de screenshots e vídeos**

* Cypress **automaticamente tira screenshots** em falhas.
* Para capturar manualmente:

```js
cy.screenshot(); // Captura o estado atual da tela
```

* Para gravação de vídeo:

```bash
npx cypress run
```

> Um vídeo de cada teste será salvo em `cypress/videos/`.

---

### 🛠️ **Depuração com recarregamento automático**

* Com `npx cypress open`, o Cypress abre em modo interativo:

  * O navegador é recarregado automaticamente a cada salvamento de arquivo.
  * Permite “ver” os testes acontecendo passo a passo.

---

### 🔄 **Execução em pipeline CI/CD**

Adicione no `.github/workflows/testes.yml`:

```yaml
name: Testes Cypress

on: [push]

jobs:
  e2e:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Instalar Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - run: npm install
      - run: npx cypress run
```

---

### Segue uma pasta zipada com arquivos para executar um teste completo com Cypress:
https://drive.google.com/file/d/1aurK9HX9afvPJJV3f8p2B2-a9xd5Z0_S/view?usp=sharing


