Here the vulnerability is cause for the backtick, which in javascript allow to introduce code which will be interpreted as code.
The backtick has another uses I will leave a explanation on the bottom

Payload: `${alert(1)}`

![[Pasted image 20250827233843.png]]

En JavaScript, los **template literals** (o **plantillas literales**) son una forma moderna de trabajar con **strings** que facilitan la interpolación de variables, expresiones y la creación de cadenas multilínea. Se introdujeron en **ES6 (2015)**.

---
## 🔹 Sintaxis

En lugar de usar comillas simples `' '` o dobles `" "`, se usan **backticks** (`` ` ``):

```javascript
const nombre = "Ivan";
const saludo = `Hola, ${nombre}!`;
console.log(saludo); // "Hola, Ivan!"
```

---

## 🔹 Características principales

### 1. **Interpolación de variables y expresiones**

Con `${ }` puedes insertar variables o cualquier expresión dentro de la cadena:

```javascript
const a = 5;
const b = 10;
console.log(`La suma de ${a} + ${b} es = ${a + b}`);
// "La suma de 5 + 10 es = 15"
```

---

### 2. **Strings multilínea sin `\n`**

Antes de ES6, para hacer saltos de línea había que usar `\n`:

```javascript
// Antes
const texto = "Línea 1\nLínea 2";
```

Con template literals:

```javascript
const texto = `Línea 1
Línea 2`;
console.log(texto);
/*
Línea 1
Línea 2
*/
```

---

### 3. **Funciones etiquetadas (Tagged templates)**

Son una característica avanzada donde una función procesa el template literal:

```javascript
function mayus(strings, ...values) {
  return strings[0] + values.map(v => v.toUpperCase()).join(" ");
}

const nombre = "ivan";
const ciudad = "dublín";

console.log(mayus`Hola ${nombre}, bienvenido a ${ciudad}`);
// "Hola IVAN BIENVENIDO A DUBLÍN"
```

Aquí la función `mayus` recibe las partes del string y las variables interpoladas para transformarlas.
