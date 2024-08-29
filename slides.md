---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Web Components - Crea tu propia etiqueta HTML
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: fade-out
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# Custom fonts
fonts:
  sans: Roboto
  serif: Roboto Slab
  mono: Fira Code

---

<div class="flex flex-col items-center justify-center h-full">
  <div class="title-container mb-12 text-center">
    <h1 class="text-4xl font-bold mb-4">¡Crea tu propia etiqueta HTML!</h1>
    <h2 class="text-2xl">Componentes nativos y sin librerías con Web Components</h2>
  </div>
  <div class="flex justify-center items-center w-full gap-8">
    <div class="speaker-info flex justify-center items-center gap-5 bg-white bg-opacity-10 p-6 rounded-lg shadow-lg max-w-xl w-full">
      <img src="/avatar.jpg" alt="Avatar" class="avatar w-28 h-28 rounded-full border-3 border-solid border-white/20 object-cover">
      <div class="info flex flex-col justify-between w-fit">
        <div>
          <h3 class="text-2xl font-semibold mb-2 mt-2">Christian Camilo Galeano</h3>
          <p class="text-xl text-gray-300">Frontend Developer | Ingeniero Mecánico</p>
        </div>
        <div class="social-links mt-2">
          <a href="https://www.linkedin.com/in/Camilodev/" target="_blank" alt="LinkedIn" title="LinkedIn Profile"
            class="text-2xl slidev-icon-btn opacity-70 !border-none !hover:text-white mr-3">
            <carbon-logo-linkedin />
          </a>
          <a href="https://github.com/CamiloGdev" target="_blank" alt="GitHub" title="GitHub Profile"
            class="text-2xl slidev-icon-btn opacity-70 !border-none !hover:text-white">
            <carbon-logo-github />
          </a>
        </div>
      </div>
    </div>
    <div class="flex flex-col items-center justify-center">
      <img src="/javaScript.png" alt="Logo 1" class="w-20 h-20 mb-4 object-contain">
      <img src="/webCom.png" alt="Logo 2" class="w-20 h-20 object-contain">
    </div>
  </div>
</div>

<style>
  .social-links a {
    transition: opacity 0.3s ease;
  }
  .social-links a:hover {
    opacity: 1;
  }
</style>

---

# Encuesta rápida

Por favor levanten la mano si:

<v-clicks>

- Actualmente trabajan con Web Components en sus proyectos
- En algún momento han trabajado o han estudiado los Web Components
- Han escuchado hablar de Web Components o conocían su existencia antes de hoy
- Es la primera vez que oyen hablar de Web Components

</v-clicks>

---

# WebComponents?? 🤔

¡No son una sola cosa!

Son un conjunto de características relacionadas con HTML, CSS y Javascript.

<div style="display: flex; justify-content: center;">
  <img src="https://lenguajejs.com/webcomponents/componentes/que-son-webcomponents/que-son-webcomponents.png" alt="Web Components Diagram" style="width: 70%; height: auto;">
</div>

## Quiero mi propia etiqueta HTML!

<!-- WebComponents es el nombre por el que se conoce a un conjunto de características relacionadas con HTML, CSS y Javascript, mediante las cuales podremos crear nuestras propias etiquetas HTML reutilizables, sin que sea necesario utilizar herramientas externas, librerías o frameworks. A estos elementos reutilizables se les suele llamar componentes. -->

---

# Cuales son esas características?

<div style="display: flex; justify-content: center;">
  <img src="https://lenguajejs.com/webcomponents/componentes/caracteristicas-webcomponents/custom-elements-templates-shadow-dom-es-modules.png" alt="Características de Web Components" style="width: 80%; height: auto;">
</div>

<!--
- características de tecnologías nativas de la plataforma web como HTML, CSS y Javascript.
- Cada se puede usar de forma independiente, pero juntas forman lo que se conoce como WebComponents.
-->

---
layout: two-cols

---

# Custom Elements

(Elementos HTML personalizados)

Son el eje centrar entorno al cual se construyen los WebComponents.

::right::
<img style="object-view-box: inset(130px 995px 0 0)" src="https://lenguajejs.com/webcomponents/componentes/caracteristicas-webcomponents/custom-elements-templates-shadow-dom-es-modules.png" alt="Características de Web Components">

<!-- De estos hablaremos mas en un momento con el demo inicial-->

---
layout: two-cols

---

# Templates

Etiqueta nativa de HTML que nos permite crear contenido inerte en una página.

```html
<template id="user-template">
  <div class="user">
    <h1>Username</h1>
    <img src="user-image.png" alt="Username">
    <a href="https://website.com/">URL</a>
  </div>
</template>
```

::right::
<img style="object-view-box: inset(100px 720px 0 270px)" src="https://lenguajejs.com/webcomponents/componentes/caracteristicas-webcomponents/custom-elements-templates-shadow-dom-es-modules.png" alt="Características de Web Components">

<!--
* No se procesa (js) durante la carga de la pagina, permanecerá «muerto» hasta clonar con Javascript.
* El navegador no invertirá recursos en su procesamiento.
* Preparar contenido reutilizable, solo consume recursos al clonar desde Javascript.
* Ejemplo la carga de la imagen.
-->

---
layout: two-cols

---

# Shadow DOM

Crear un marcado HTML (DOM, una estructura HTML) particular en un elemento HTML.

De esta forma, además del DOM global del documento, tenemos uno particular en ese elemento.

```html
<div class="element">
  #shadow-root
    <div class="inner-element">
      ...
    </div>
</div>
```

::right::
<img style="object-view-box: inset(130px 520px 0 530px)" src="https://lenguajejs.com/webcomponents/componentes/caracteristicas-webcomponents/custom-elements-templates-shadow-dom-es-modules.png" alt="Características de Web Components">

<!--
* Una de las mas interesantes pero también mas complejas
* Su misión es crear una estructura aislada.
* Una forma de crear estructuras con estilos CSS locales, que sólo afectan a su interior y no son afectados por el exterior.
-->

---
layout: two-cols

---

# CSS Scopes / Shadow Parts

Estrategias y mecánicas especializadas para tratar CSS en los webComponentes.

<v-click>

## CSS Scopes

Surgen a raíz del CSS en los WebComponents. Podemos dar estilo a componentes con un Shadow DOM.
</v-click>

<v-click>

## CSS Shadow Parts

Una forma de exponer zonas de un componente para darle estilo desde su exterior.
</v-click>

::right::
<img style="object-view-box: inset(120px 0 0 955px)" src="https://lenguajejs.com/webcomponents/componentes/caracteristicas-webcomponents/custom-elements-templates-shadow-dom-es-modules.png" alt="Características de Web Components">

<!--
* Una de las mas interesantes pero también mas complejas
* Su misión es crear una estructura aislada.
* Una forma de crear estructuras con estilos CSS locales, que sólo afectan a su interior y no son afectados por el exterior.
-->

---

# ¿Por qué usar WebComponents?

<v-clicks>

- Reutilización

- Encapsulación

- Interoperabilidad

- Mantenibilidad
</v-clicks>

<!--
Los WebComponents persiguen varios objetivos, entre los que se encuentran los siguientes:
* Reutilización: evitar repetir código.
* Encapsulación: aislar, usar unos dentro de otros para construir nuevos.
* Interoperabilidad: intercambio de información, que aseguren funcionar en cualquier dispositivo, independientemente de su tecnología.
* Mantenibles: en el tiempo la cantidad de líneas de código se hace mayor y más complicado. Necesitamos poder enfocarnos en características concretas, usando HTML, CSS y Javascript que sólo influya a dicha característica.
-->

---

# Donde se sitúan los WebComponents?

¿En que punto se sitúan algunas de las herramientas que mas usamos actualmente?

<div style="display: flex; justify-content: center;">
  <img src="https://lenguajejs.com/webcomponents/componentes/que-son-webcomponents/webcomponents-vs-frameworks-diferencias.png" alt="Pyramid of web development tools" style="width: 80%; height: auto;">
</div>

---
layout: two-cols

---

## WebComponents

- Extiende el lenguaje HTML para crear una etiqueta HTML propia.
- Componentes muy cerca de la plataforma web, del navegador, del lado del cliente.
- Solo cargas el código asociado al componente que estas usando.
- Código imperativo.
- Experiencia de desarrollo mas compleja.
- Se ejecuta todo en el cliente.

::right::

## Frameworks

- Simula crear una etiqueta HTML
- Componentes abstraídos de la plataforma web, operando en una capa virtual (Virtual DOM) antes de renderizar al navegador.
- No es un componente real
- Implica la carga de la librería ó framework.
- Enfoque declarativo, ej. React.
- Experiencia de desarrollo mas sencilla.
- Brinda soporte para el lado del servidor.

---

# Quiero mi propia etiqueta HTML!

<v-click>

¿Que crees que pasara si escribo esto en mi HTML?

```html
<my-component></my-component>
```

</v-click>

<v-click>

<div class="mt-8">

## Nombres de las etiquetas HTML

<div style="display: flex; justify-content: center;">
  <img src="/customElements.png" alt="" style="width: 100%; height: auto;">
</div>

</div>

</v-click>

<!--
* npx servor . index.html --reload        // para servir el archivo
* El estándar: una sola palabra
* custom: al menos dos fragmentos separados por un guión, evita colisión con los elementos standard
* nombres que eviten colisión con elementos de otras librerías, no sabes cuando la vamos a necesitar.
 -->

---

# Nuestro custom element

Es por defecto de tipo `display: inline` , pero podemos cambiarlo.

<div class="w-full flex gap-4">
  <div class="w-1/2">

```html
<app-element>
  Contenido de nuestro elemento personalizado
</app-element>
```

  </div>
  <div class="w-1/2">

```css
app-element {
  display: block;
  width: 125px;
  height: 125px;
  padding: 5px;
  background: black;
  color: white;
}
```

  </div>
</div>

<v-click>

## ¿Es realmente un Custom Element?

```html
<app-element></app-element>
<element></element>

<script>
const appElement = document.querySelector("app-element");
const element = document.querySelector("element");

console.log("<app-element>: ", appElement.constructor.name);  // HTMLElement
console.log("<element>: ", element.constructor.name);         // HTMLUnkownElement
</script>
```

</v-click>

<!-- Ya sabemos crearlos pero aun nos falta darles funcionalidad para poder llamarlos WebComponents -->

---

# Creando WebComponents

## ¿Cómo podemos darle funcionalidad a nuestro Custom Element?

<div class="w-full flex gap-4">
  <div class="w-1/2 overflow-hidden">

````md magic-move {lines: true}
```html
<!-- index.html -->

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WebComponents</title>
</head>

<body>
    <img src="https://avatars.githubusercontent.com/u/55265206?s=200&v=4" alt="MedellinJS Logo">
</body>

</html>
```

```html{10,14}
<!-- index.html -->

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>WebComponents</title>
  <script type="module" src="index.js"></script>
</head>

<body>
  <medjs-header></medjs-header>
</body>

</html>
```

````

  </div>
  <div class="w-1/2">

<v-click at="1">

```js
// index.js

import "./components/MedjsHeader.js";
import "./components/OtroComponente.js";

//....
```

```js
// app-element-one.js
console.log("Saludo desde el modulo MedjsHeader.js");
```

</v-click>

  </div>
</div>

<!--
* Ya importamos el modulo para el componente
* Pero aun la etiqueta no esta conectada con el componente
* Que pasa si quito el type="module" del script?
-->

---

# Creando WebComponents

## ¿Cómo podemos darle funcionalidad a nuestro Custom Element?

Creamos una clase Javascript que mejorará nuestro custom element.

<v-click at='1'>
Asociación del elemento HTML con la clase Javascript.
</v-click>

````md magic-move {lines: true}
```js
class MedjsHeader extends HTMLElement {
  constructor() {
    super();
    console.log("Custom Element inicializado: ", this);
  }
}
```

```js{8}
class MedjsHeader extends HTMLElement {
  constructor() {
    super();
    console.log("Custom Element inicializado: ", this);
  }
}

customElements.define("medjs-header", MedjsHeader);
```
````

<v-click>

Con todo esto ya podemos dotar de funcionalidad a nuestro custom element, con la ayuda de javaScript y métodos del DOM.

</v-click>

<!--
* Extendemos de la clase HTMLElement
* sin no se define el constructor, se ejecutará del padre
* en caso de definir el constructor, es necesario llamar a super() para inicializar la clase padre
* agregamos
* el detalle más importante: la asociación del elemento HTML con la clase Javascript.

-->

---

# ¿Como podemos usar nuestro componente desde JavaScript?

<v-click>

## A través del DOM

```js
// Utilizando el DOM
const appElement = document.createElement("app-element");
document.body.append(appElement);
```

</v-click>

<v-click>

## A través de instancias

```js
export class AppElement extends HTMLElement {
  /* ... */
}
```

```js
import { AppElement } from "./components/AppElement.js";

const appElement = new AppElement();
document.body.append(appElement);
```

</v-click>

---

# ¿HTML desde un componente?

No queremos repetir código HTML una y otra vez.
Queremos escribirlo en un componente, y utilizar el componente cada vez que lo necesitemos.

```html
<!-- En lugar de escribir esto... -->
<div class="card">
  <h1>Andres</h1>
  <img src="avatarAndres.png" alt="Avatar de Andres">
  ...
</div>

<div class="card">
  <h1>Carlos</h1>
  <img src="avatarCarlos.png" alt="Avatar de Carlos">
  ...
</div>

<!-- Queremos escribir esto... -->
<user-card name="Andres"></user-card>
<user-card name="Carlos"></user-card>
```

---

# ¿Como escribir HTML en un componente?

- Escribir el código HTML mediante un `string`
- Escribir el código HTML mediante métodos del DOM
- Escribir el código HTML mediante plantillas
- Escribir el código HTML mediante librerías

En esta charla solo abordaremos las dos primeras.

---

# HTML a través de strings

Escribir el código HTML mediante un `string`.

Luego insertarlo en el componente.

Para esto ultimo contamos con propiedades del DOM como `innerHTML` ó `textContent`.

<div v class="w-full flex gap-4">
<div class="w-1/2 overflow-hidden">
<v-click>

```js
class AppElement extends HTMLElement {
  constructor() {
    super();
    this.innerHTML = "<div>Mi componente</div>";
  }
}

customElements.define("app-element", AppElement);
```

</v-click>
</div>

<div class="w-1/2 overflow-hidden">
<v-click>

## Usando string templates

```js
class AppElement extends HTMLElement {
  constructor() {
    super();
    this.innerHTML = /* html */`
      <div class="card">
        <h1>Mi componente</h1>
      </div>`;
  }
}

customElements.define("app-element", AppElement);
```

</v-click>
</div>
</div>

---

# HTML a través del DOM

<div style="display: flex; justify-content: center;">
  <img src="./metodosDom.png" alt="Pyramid of web development tools" style="width: 100%; height: auto;">
</div>

```js
class AppElement extends HTMLElement {
  constructor() {
    super();
    const card = document.createElement("div");
    card.classList.add("card");
    this.append(card);

    const heading = document.createElement("h1");
    heading.textContent = "Mi componente";
    card.append(heading);
  }
}

customElements.define("app-element", AppElement);
```

---

# Evitar la carga innecesaria

````md magic-move {lines: true}
```js{5-11}
class MedjsHeader extends HTMLElement {
  constructor() {
    super();
    console.log("Custom Element inicializado: ");
    this.innerHTML = /*html*/ `
      <header>
          <img src="https://avatars.githubusercontent.com/u/55265206?s=200&v=4" alt="MedellinJS Logo">
          <h1>MedellinJS</h1>
      </header>
      `;
  }
}
customElements.define("medjs-header", MedjsHeader);
```

```js{7-15}
class MedjsHeader extends HTMLElement {
  constructor() {
    super();
    console.log("Custom Element inicializado: ");
  }

  connectedCallback() {
    console.log("Custom Element conectado: ");
    this.innerHTML = /*html*/ `
      <header>
          <img src="https://avatars.githubusercontent.com/u/55265206?s=200&v=4" alt="MedellinJS Logo">
          <h1>MedellinJS</h1>
      </header>
      `;
  }
}

customElements.define("medjs-header", MedjsHeader);
```

```js
class MedjsHeader extends HTMLElement {
  connectedCallback() {
    console.log("Custom Element conectado: ");
    this.innerHTML = /*html*/ `
      <header>
          <img src="https://avatars.githubusercontent.com/u/55265206?s=200&v=4" alt="MedellinJS Logo">
          <h1>MedellinJS</h1>
      </header>
      `;
  }
}
customElements.define("medjs-header", MedjsHeader);

```

```js{4,7-15}
class MedjsHeader extends HTMLElement {
  connectedCallback() {
    console.log("Custom Element conectado: ", this);
    this.render();
  }

  render() {
    this.innerHTML = /*html*/ `
      <header>
          <img src="https://avatars.githubusercontent.com/u/55265206?s=200&v=4" alt="MedellinJS Logo">
          <h1>MedellinJS</h1>
      </header>
      `;
  }
}

customElements.define("medjs-header", MedjsHeader);
```
````

<v-click at="1">

Solo queremos ejecutar el código si el componente entra en el HTML.

</v-click>

<v-click at="2">

Y al no estar usando el constructor, podemos eliminarlo.

</v-click>

<v-click at="3">

Es usual crear un método `render()` para la creación del HTML.

</v-click>

<!--
Si lo dejamos en el constructor, se ejecuta cuando se instancia el componente con el método customElements.define
 -->

---

# Atributos

```html
<!-- HTML -->
<body>
    <medjs-header title="Medellin js"></medjs-header>
</body>
```

````md magic-move {lines: true}
```js{4,12}
// js
class MedjsHeader extends HTMLElement {
  connectedCallback() {
    this.title = this.getAttribute("title") ?? "MedellinJS";
    this.render();
  }

  render() {
    this.innerHTML = /*html*/ `
        <header>
            <img src="https://avatars.githubusercontent.com/u/55265206?s=200&v=4" alt="MedellinJS Logo">
            <h1>${this.title}</h1>
        </header>
        `;
  }
}

customElements.define("medjs-header", MedjsHeader);
```
````

<!--
* Las llamadas props o propiedades en los frameworks como React
* Solo aceptan strings
* a diferencia de React, no se pueden pasar objetos o funciones
-->

---

# Atributos

Métodos que permiten comprobar si existen ciertos atributos o el valor que contienen

<div style="display: flex; justify-content: center;">
  <img src="./atributos.png" alt="Pyramid of web development tools" style="width: 90%; height: auto;">
</div>

```js
class AppElement extends HTMLElement {
  constructor() {
    super();
    console.log("¿Tiene atributos?: ", this.hasAttributes()); // true
    console.log("Número de atributos: ", this.getAttributeNames().length); // 2
    console.log("Atributos: ", this.getAttributeNames()); // ["name", "devname"]
    console.log("¿Existe name?: ", this.hasAttribute("name")); // true
    console.log("Valor de name: ", this.getAttribute("name")); // Mi componente
    console.log("Atributos inexistentes: ", this.getAttribute("uhghae")); // null
  }
}
customElements.define("app-element", AppElement);
```

---

# Atributos

## Modificación de atributos HTML

<div style="display: flex; justify-content: center;">
  <img src="./modAtributos.png" alt="Pyramid of web development tools" style="width: 100%; height: auto;">
</div>

---

# Ciclo de vida de un WEbComponent

<div style="display: flex; justify-content: center;">
  <img src="https://lenguajejs.com/webcomponents/funcionalidad/ciclo-vida-webcomponent/webcomponents-lifecycle-diagram.png" alt="Pyramid of web development tools" style="width: 60%; height: auto;">
</div>

---

# Ciclo de vida de un WEbComponent

## Métodos del ciclo de vida

<div style="display: flex; justify-content: center;">
  <img src="./cicloDeVida.png" alt="Pyramid of web development tools" style="width: 100%; height: auto;">
</div>
---

# Shadow DOM

## Insertar el Shadow DOM

````md magic-move {lines: true}
```js{4}
class MedjsHeader extends HTMLElement {
  constructor() {
    super();
    this.attachShadow({ mode: "open" });
  }

  connectedCallback() {
    ...
  }

  render() {
    ...
  }

customElements.define("medjs-header", MedjsHeader);

```

```js{4,12}
class MedjsHeader extends HTMLElement {
  constructor() {
    super();
    this.attachShadow({ mode: "open" });
  }

  connectedCallback() {
    ...
  }

  render() {
    this.shadowRoot.innerHTML = /*html*/ `
      ...
    `;
  }

customElements.define("medjs-header", MedjsHeader);

```
````

<v-click at="1">

Cons esto aislamos nuestro componente y sun elementos del resto del DOM.

</v-click>

<!--
Ahora todo el contenido del componente esta oculto en el shadowRoot, mostrar en el navegador
-->

---

# CSS al WebComponent

## Desde el DOM global

Podemos aplicar estilos desde el DOM global al shadowRoot.

```css
app-element {
  display: block;
  background: indigo;
  color: white;
  padding: 10px;
  margin: 5px;
}
```

---

# CSS al WebComponent

Con la pseudo-clase `:host`

<div class="w-full flex gap-4">
  <div class="w-1/2 overflow-hidden">
```js
this.shadowRoot.innerHTML = /* html */`
  <style>
    :host {
      display: block;
      background: indigo;
      color: white;
      padding: 10px;
      margin: 5px;
    }
    :host-context(.dark) {
      background: black;
    }
    span {
      font-weight: bold;
      vertical-align: super;
      font-size: small;
      color: gold;
    }
  </style>
  <div class="element">
    AppElement <span>New!</span>
  </div>
`
```
  </div>
  <div class="w-1/2 overflow-hidden">
```html
<app-element></app-element>
<app-element disabled></app-element>
```
  </div>
</div>
---

# CSS al WebComponent

Variables CSS/ Custom Properties

```css
:root {
  --gradient: linear-gradient(indigo, blueviolet);
}

.element {
  background: var(--gradient, purple);
}

.warning {
  --gradient: red;
  background: var(--gradient, black);
}
```

---

# Uso de librearías de WebComponents


<!--
* iniciar el package.json: npm init -y
* instalar vite: npm install vite
* incorporar 2 script para dev y para build con vite en el package.json:
  "dev": "vite dev",
  "build": "vite build"
* instalar el componente: https://dile-components.polydile.com/components/dile-slide-show/
* lo importo en el index.js
* inicio el servidor con run dev
 -->
