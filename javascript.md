Aqui está um resumo objetivo e claro dos principais tópicos da linguagem JavaScript:

---

### 📌 **1. Tipos de Dados**

* Primitivos: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`
* Estruturados: `object`, `array`, `function`

---

### 📌 **2. Variáveis**

* `var`: escopo de função (evite usar)
* `let`: escopo de bloco
* `const`: escopo de bloco, valor constante

---

### 📌 **3. Operadores**

* Aritméticos: `+`, `-`, `*`, `/`, `%`, `**`
* Comparação: `==`, `===`, `!=`, `!==`, `<`, `>`, `<=`, `>=`
* Lógicos: `&&`, `||`, `!`
* Atribuição: `=`, `+=`, `-=`, etc.
* Ternário: `condição ? valor1 : valor2`

---

### 📌 **4. Estruturas de Controle**

* Condicionais: `if`, `else`, `switch`
* Laços: `for`, `while`, `do...while`, `for...of`, `for...in`

---

### 📌 **5. Funções**

* Declarativas: `function nome() {}`
* Expressões: `const nome = function() {}`
* Arrow functions: `const nome = () => {}`

---

### 📌 **6. Objetos e Arrays**

* Objetos: `{ chave: valor }`
* Acesso: `obj.chave` ou `obj['chave']`
* Arrays: `[1, 2, 3]`
* Métodos úteis: `map`, `filter`, `reduce`, `forEach`

---

### 📌 **7. Manipulação de DOM (em navegadores)**

* Seleção: `document.querySelector()`, `getElementById()`
* Alteração: `element.textContent`, `element.innerHTML`
* Eventos: `addEventListener('click', function)`

---

### 📌 **8. JSON**

* Converter para string: `JSON.stringify(obj)`
* Converter para objeto: `JSON.parse(string)`

---

### 📌 **9. Assincronismo**

* `setTimeout`, `setInterval`
* Promises: `.then()`, `.catch()`
* `async/await`

---

### 📌 **10. Módulos (ES6)**

* Exportar: `export` ou `export default`
* Importar: `import { nome } from './modulo.js'`

---

Abaixo estão os principais tópicos da linguagem JavaScript detalhados com **3 exemplos práticos** para cada item:

---

### 📌 **1. Tipos de Dados**

**String**

```javascript
let nome = "João";
console.log(nome.toUpperCase()); // "JOÃO"
```

**Number**

```javascript
let preco = 10.5;
console.log(preco * 2); // 21
```

**Boolean**

```javascript
let ativo = true;
console.log(!ativo); // false
```

---

### 📌 **2. Variáveis**

**var**

```javascript
var idade = 30;
idade = 31;
console.log(idade); // 31
```

**let**

```javascript
let cidade = "SP";
cidade = "RJ";
console.log(cidade); // "RJ"
```

**const**

```javascript
const PI = 3.14;
// PI = 3.1415; // Erro!
console.log(PI);
```

---

### 📌 **3. Operadores**

**Aritméticos**

```javascript
let total = 10 + 5;
console.log(total); // 15
```

**Comparação**

```javascript
console.log(5 === "5"); // false
```

**Lógicos**

```javascript
console.log(true && false); // false
```

---

### 📌 **4. Estruturas de Controle**

**if / else**

```javascript
let idade = 20;
if (idade >= 18) {
  console.log("Maior de idade");
} else {
  console.log("Menor de idade");
}
```

**switch**

```javascript
let cor = "azul";
switch(cor) {
  case "vermelho":
    console.log("Cor quente");
    break;
  case "azul":
    console.log("Cor fria");
    break;
}
```

**for**

```javascript
for (let i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}
```

---

### 📌 **5. Funções**

**Declarativa**

```javascript
function saudacao(nome) {
  return "Olá, " + nome;
}
console.log(saudacao("Maria"));
```

**Expressão**

```javascript
const dobro = function(x) {
  return x * 2;
};
console.log(dobro(4)); // 8
```

**Arrow function**

```javascript
const soma = (a, b) => a + b;
console.log(soma(3, 7)); // 10
```

---

### 📌 **6. Objetos e Arrays**

**Objeto**

```javascript
let pessoa = { nome: "Ana", idade: 25 };
console.log(pessoa.nome); // "Ana"
```

**Array**

```javascript
let frutas = ["maçã", "banana", "uva"];
console.log(frutas[1]); // "banana"
```

**Métodos de array**

```javascript
let numeros = [1, 2, 3];
let dobro = numeros.map(n => n * 2);
console.log(dobro); // [2, 4, 6]
```

---

### 📌 **7. Manipulação de DOM**

**Selecionar elemento**

```javascript
let titulo = document.querySelector("h1");
console.log(titulo.textContent);
```

**Alterar conteúdo**

```javascript
document.getElementById("mensagem").textContent = "Bem-vindo!";
```

**Adicionar evento**

```javascript
document.querySelector("button").addEventListener("click", () => {
  alert("Botão clicado!");
});
```

---

### 📌 **8. JSON**

**Objeto → JSON**

```javascript
let obj = { nome: "João" };
let json = JSON.stringify(obj);
console.log(json); // '{"nome":"João"}'
```

**JSON → Objeto**

```javascript
let texto = '{"idade":30}';
let dados = JSON.parse(texto);
console.log(dados.idade); // 30
```

**Uso comum com fetch**

```javascript
fetch("https://api.exemplo.com")
  .then(res => res.json())
  .then(data => console.log(data));
```

---

### 📌 **9. Assincronismo**

**setTimeout**

```javascript
setTimeout(() => {
  console.log("Atrasado 1s");
}, 1000);
```

**Promise**

```javascript
let promessa = new Promise(resolve => resolve("OK"));
promessa.then(res => console.log(res)); // "OK"
```

**async/await**

```javascript
async function teste() {
  let resposta = await Promise.resolve("Async");
  console.log(resposta);
}
teste();
```

---

### 📌 **10. Módulos (ES6)**

**Exportar**

```javascript
// arquivo: saudacao.js
export function ola() {
  return "Olá!";
}
```

**Importar**

```javascript
// arquivo: app.js
import { ola } from "./saudacao.js";
console.log(ola()); // "Olá!"
```

**Export default**

```javascript
// arquivo: utils.js
export default function soma(a, b) {
  return a + b;
}
```

---

Segue um exemplo completo em um único arquivo `.html` com todos os tópicos e exemplos práticos de JavaScript listados anteriormente. Você pode salvar este conteúdo como `exemplos.html` e abrir no navegador:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Exemplos de JavaScript</title>
</head>
<body>
  <h1>Exemplos de JavaScript</h1>
  <p id="mensagem">Texto original</p>
  <button>Clique aqui</button>

  <script type="module">
    // 1. Tipos de Dados
    let nome = "João";
    let preco = 10.5;
    let ativo = true;
    console.log(nome.toUpperCase());
    console.log(preco * 2);
    console.log(!ativo);

    // 2. Variáveis
    var idade = 30;
    let cidade = "SP";
    const PI = 3.14;
    console.log(idade, cidade, PI);

    // 3. Operadores
    console.log(10 + 5);
    console.log(5 === "5");
    console.log(true && false);

    // 4. Estruturas de Controle
    if (idade >= 18) {
      console.log("Maior de idade");
    }
    switch (cidade) {
      case "SP":
        console.log("São Paulo");
        break;
    }
    for (let i = 0; i < 3; i++) {
      console.log(i);
    }

    // 5. Funções
    function saudacao(nome) {
      return "Olá, " + nome;
    }
    const dobro = function(x) {
      return x * 2;
    };
    const soma = (a, b) => a + b;
    console.log(saudacao("Maria"));
    console.log(dobro(4));
    console.log(soma(3, 7));

    // 6. Objetos e Arrays
    let pessoa = { nome: "Ana", idade: 25 };
    let frutas = ["maçã", "banana", "uva"];
    let numeros = [1, 2, 3];
    console.log(pessoa.nome);
    console.log(frutas[1]);
    console.log(numeros.map(n => n * 2));

    // 7. Manipulação de DOM
    document.getElementById("mensagem").textContent = "Bem-vindo!";
    document.querySelector("button").addEventListener("click", () => {
      alert("Botão clicado!");
    });

    // 8. JSON
    let obj = { nome: "João" };
    let json = JSON.stringify(obj);
    console.log(json);
    let texto = '{"idade":30}';
    let dados = JSON.parse(texto);
    console.log(dados.idade);
    // fetch comentado por ser externo
    // fetch("https://api.exemplo.com").then(res => res.json()).then(data => console.log(data));

    // 9. Assincronismo
    setTimeout(() => {
      console.log("Atrasado 1s");
    }, 1000);

    let promessa = new Promise(resolve => resolve("OK"));
    promessa.then(res => console.log(res));

    async function testeAsync() {
      let resposta = await Promise.resolve("Async");
      console.log(resposta);
    }
    testeAsync();

    // 10. Módulos - exemplo simplificado aqui no mesmo arquivo
    function ola() {
      return "Olá!";
    }
    console.log(ola());
  </script>
</body>
</html>
```


