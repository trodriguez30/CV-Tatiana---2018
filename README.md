# Crea tu CV con Github Pages

Workshop de PionerasDev - 15 de Diciembre de 2018

## Estructura

Nuestra hoja de vida se dividirá de la siguiente manera:

1. Header o cabecera
2.  Secciones:
    - Perfil
    - Habilidades
    - Formación
    - Experiencia
    - Cursos
    - Contáctame
3. Footer o pie de página

## Empezamos el desarrollo!!!

En una carpeta creamos un archivo: **index.html** con la estructura básica:

```html
<!DOCTYPE html>
<html lang="en">
<head>
 <meta charset="UTF-8">
 <meta name="viewport" content="width=device-width, initial-scale=1.0">
 <meta http-equiv="X-UA-Compatible" content="ie=edge">
 <title>CV - Tatiana Rodríguez</title>
 <meta name="description" content="simple CV con HTML and CSS">
 <meta name="author" content="Tatiana Rodriguez">
 <title>CV con Github Pages</title>
</head>
<body>

</body>
</html>
```

El flujo de desarrollo será:

- [x] Agregamos código HTML según la estructura.
- [x] Cambiamos el estilo desde un archivo .css

### Header o cabecera

Esta parte de la estructura nos servirá para mostrar nuestro avatar y colocar una frase con la cual nos identifiquemos.

Necesitamos 2 imagenes:

1. Un avatar (preferiblemente una foto tuya) de 150px. 
2. Una imagen de fondo (Relacionada con tu área de trabajo).

Las cuales guardaremos en una carpeta llamada **img** en la misma ruta del index.html.

Ahora si:

Coloquemos esto en el index.html

```html
<body>
  <header>
    <div>
    <img src="./img/avatar.jpg" />
    </div>
    <h1>Tatiana Rodríguez</h1>
    <p>“Todos tus sueños pueden hacerse realidad si tienes el coraje de
    perseguirlos”</p>
 </header>
</body>
```

Para darle estilo creamos un archivo llamado **style.css**

Y lo conectamos a nuestro index.html así:

```html
<link rel="stylesheet" href="style.css">
```

Y en ese nuevo archivo agregamos:

```css
@import url('https://fonts.googleapis.com/css?family=Raleway');
body {
 margin: 0;
 font-family: 'Raleway';
 font-size: 16px;
 line-height: 1.8em;
}
header, main, footer {
 margin: 0 auto;
}
header {
 padding: 2em;
 text-align: center;
 background-image: url('./img/bg.jpg');
 background-size: cover;
 background-position: fixed;
 color: white;
 font-weight: bold;
}
header img {
 border-radius: 50%;
 max-width: 150px;
}
header p{
 text-align: center;
}
```

### Secciones

Después del header agregaremos el contenido de la hoja de vida, dentro de la siguiente etiqueta:

```html
<main>

</main>
```

**1.Perfil**

Coloca una descripción de tu perfil en el área de conocimiento en el que te desempeñes:

```html
<section>
 <h3>Perfil:</h3>
 <p>Describe tu perfil aquí</p>
</section>
```

Y en el style.css:

```css
section{
 margin: 1em;
 padding: 1em;
}
h3 {
 text-transform: uppercase;
}
h3, h4 {
 font-weight: bold;
} 
5
main {
 max-width: 1140px;
}
p{
 text-align: justify;
}
```

**2. Habilidades**

Donde tenemos:

- Conocimientos avanzados
- Conocimientos básicos
- Lenguaje – nivel


```html
<section>
 <h3>Habilidades</h3>
 <div class='skills'>
 <div class='column'>
 <h4>Conocimientos avanzados</h4>
 <ol>
 <li>C. Avanzado #1</li>
 <li> C. Avanzado #2</li>
 <li> C. Avanzado #3</li>
 </ol>
 </div>
 <div class='column'>
 <h4>Conocimientos básicos</h4>
 <ol>
 <li>C. Básico #1</li>
 <li> C. Básico #2</li>
 </ol>
 </div>
6
 <div>
 <h4>Lenguajes</h4>
 <p>Español - Nativo</p>
 <p>Inglés - Intermedio - B1</p>
 </div>
 </div>
 </section>
```

En el style.css:

```css
@import url('https://fonts.googleapis.com/css?family=Abril+Fatface');
.skills {
 display: -ms-flexbox;
 display: flex;
 -ms-flex-wrap: wrap;
 flex-wrap: wrap;
}
.skills .column {
 -ms-flex: 0 0 50%;
 flex: 0 0 50%;
 max-width: 50%;
}
.skills .column ul{
 list-style-type: none;
}
.skills .column ol{
 list-style: none;
 counter-reset: my-awesome-counter;
 display: flex;
 flex-wrap: wrap;
 margin: 0;
 padding: 0;
}
.skills .column ol li {
 counter-increment: my-awesome-counter;
 display: flex;
 width: 50%;
 font-size: 1em;
 margin-bottom: 0.5em;
}
.skills .column ol li::before {
 content: "0" counter(my-awesome-counter);
 font-weight: bold;
 font-size: 1.5em;
 margin-right: 0.5em;
 font-family: 'Abril Fatface', serif;
 line-height: 1;
} 
```

**3. Formación**

Colocamos los detalles de nuestra formación:

```html
<section>
 <h3>Formación</h3>
 <article>
 <div class='degree'>
 <span>2013</span> <strong>Bachiller académico</strong>
 </div>
 <div class="school">
 Colegio Emilio Sotomayor
 </div>
 </article>
 </section>
```

El contenido encerrado en la etiqueta *<article>* podemos repetirlo las veces que sea necesaria para
completar la información de nuestra formación.

```css
article{
 margin-bottom: 0.5em;
}
.degree{
 text-transform: capitalize;
}
.degree span {
 color: #386e6a;
 text-decoration: underline;
}
```

**4. Experiencia**

Para nuestra experiencia necesitaremos un archivo de estilo externo.

Lo descargaremos del siguiente link:

[timeline.css] (https://drive.google.com/file/d/12L7wJTBT9ZNoLKASbrQFjjjR00dFkQ7o/view)

Lo conectamos con nuestro index.html:

```html
<link rel="stylesheet" href="timeline.css">
```

Y agregamos:

```html
<section>
 <h3>Experiencia</h3>
 <article>
 <ul class="timeline">
 <!-- Item 1 -->
 <li>
 <div class="direction-r">
 <div class="flag-wrapper">
 <span class="flag">Cargo</span>
 <span class="time-wrapper"><span class="time">Fecha<span></span>
 </div>
 <div class="desc">
 <p><strong>Descripción:</strong> </p>
 <ul class="job-description">
 <li>Detalle #1</li>
 <li> Detalle #2</li>
 <li> Detalle #3</li>
 </ul>
 </div>
 </div>
 </li>
 <!-- Item 2 -->
 <li>
 <div class="direction-l">
 <div class="flag-wrapper">
 <span class="flag">Cargo</span>
 <span class="time-wrapper"><span class="time">Fecha<span></span>
 </div>
 <div class="desc">
 <p><strong>Descripción:</strong> </p>
 <ul class="job-description">
 <li> Detalle #1</li>
 <li> Detalle #2li>
 <li> Detalle #3</li>
 </ul>
 </div>
 </div>
 </li>
 </ul>
 </article>
</section>
```

Solo debemos **tener en cuenta** la ubicación en la que se muestra el trabajo, donde solo es modificar:

*direction-l* se ubica hacia la izquierda.
*direction-r* se ubica hacia la derecha.

**5. Cursos virtuales**

Esta área servirá para mostrar los cursos virtuales que hemos realizado y una opción para colocar el material complementario por medio de una carpeta en **Drive**, ya sea certificados, diplomas, etc.D

```html
<section>
 <h3>Cursos virtuales</h3>
 <article class='course'>
 <div class='title'>
 <h4>Google: Curso de introducción al desarrollo web (Parte 1)</h4>
 </div>
 <div class="description">
 <p>Curso de 40h de duración, primera parte de introducción al
desarrollo web con los siguientes módulos: Historia de la web, funcionamiento,
escritura web, publicación, web correcta</p>
 </div>
 </article>
 <a
href="https://drive.google.com/drive/folders/1ApXJlQ1hzBRbC5VirwhHGGYkc4SOZKxX?usp=sh
aring">
 <button>
 Material complementario
 </button>
 </a>
 </section>
```

El estilo en css será:

```css
.course {
 display: -ms-flexbox;
 display: flex;
 -ms-flex-wrap: wrap;
 flex-wrap: wrap;
}
.course .title {
 color: #386e6a;
 -ms-flex: 0 0 33.3%;
 flex: 0 0 33.3%;
 max-width: 33%;
}
.course .description {
 -ms-flex: 0 0 66.6%;
 flex: 0 0 66.6%;
 max-width: 66.6%;
}
.course .description p {
 padding-left: 1em;
}
a button{
 font-size: 1em;
 background-color: #fff;
 color: #386e6a;
 border: none;
 padding: 15px 32px;
 text-align: center;
 text-decoration: none;
 display: inline-block;
 font-weight: bold;
 border: 3px solid #386e6a;
}
a button:hover{
 background-color: #386e6a;
 c
```
**6. Contáctame**

Para colocar nuestras redes sociales

Colocamos lo siguiente en el *head* para acceder a una fuente tipográfica:

```html
<link rel="stylesheet"
href="https://use.fontawesome.com/releases/v5.0.13/css/all.css" integrity="sha384-
DNOHZ68U8hZfKXOrtjWvjxusGo9WQnrNx2sqG0tfsghAvtVlRW3tvkXWZh58N9jp"
crossorigin="anonymous">
```
y en el *body*:

```html
<section>
 <div class="social">
 <h3>Contactame</h3>
 <a href="https://www.facebook.com/tatianar3/" target="_blank">
 <i class="fab fa-facebook-f"></i>
 Tatiana Rodríguez
 </a>
 <a href="https://github.com/trodriguez30" target="_blank">
 <i class="fab fa-github-alt"></i>
 trodriguez30
 </a>
 <a href="https://www.instagram.com/tatianarodriguezp_" target="_blank">
 <i class="fab fa-instagram"></i>
 @tatianarodriguezp_
 </a>
 <a href="https://www.linkedin.com/in/tatiana-paola-rodr%C3%ADguez-pacheco86a582141/" target="_blank">
 <i class="fab fa-linkedin-in"></i>
 Tatiana Paola Rodríguez Pacheco
 </a>
 <p>
 <i class="fab fa fa-envelope"></i>
 tatianarodriguezpacheco@gmail.com
 </p>
 </div>
```

Style.css:

```css
.social, .social p{
 text-align: center;
}
.social .fab {
 border: 1px solid white;
 border-radius: 50%;
 font-size: 1.5em;
 width: 1.5em;
 height: 1.5em;
 line-height: 1.5em;
 margin: 5px;
 text-align: center;
}
.social .fab {
 color: black;
}
.social a {
 color: black;
 text-decoration: none;
}
.social a:hover {
 opacity: 0.5;
}
```
### Pie de página

Agregamos nuestro nombre y el año:

```html
<footer>
 <p>Tatiana Rodriguez / 2018 </p>
</footer>
```

Con su respectivo css:

```css
footer {
 padding: 1em 1.5em;
 background: #386e6a;
 color: white;
 text-align: center;
}

footer p{
 text-align: center;
}
```

###Detalles finales!!!

*¡Ya casi tenemos nuestra hoja de vida completa!*
Solo falta añadir los detalles finales:

Agregamos en el style.css

```css
@media only screen and (max-width: 768px) {
 .course {
 display: block;
 }
 .course .title, .course .description {
 max-width: 100%;
 }
 footer {
 text-align: center;
 }
 .social a {
 display: block;
 }
 }

@media only screen and (max-width: 576px) {
 .skills {
 display: block;
 }
 .skills .column {
 max-width: 100%;
 }
 footer {
 text-align: center;
 }
}
```

#¡¡¡Y listo!!!
##Ya tenemos nuestra hoja de vida desarrollada

###Autores

- Tatiana Rodríguez