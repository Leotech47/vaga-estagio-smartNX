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

