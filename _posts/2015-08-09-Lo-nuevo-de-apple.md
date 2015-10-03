---
layout:     post
title:      como usar bootstrap en Ruby on Rails
date:       2015-08-09 15:31:19
author:     Leonel Alfonso

categories: rails ruby
thumbnail:  heart
tags:
 - rails
 - ruby

 - bootstrap
---
![bootstrap](https://andresad13.files.wordpress.com/2015/08/bootstrap.png?w=660)

boostrap es uno de los frameworks mas populares para usar CSS y JS que convierte el desarrollo frontend en una manera ágil y fácil de trabajar, lo puedes usar en todos los dispositivos, en todas las formas y todos los tamaños , lo puedes usar con tus proyectos en rails con este tutorial.

<hr>

1. instalar la gema.

para usar bootstrap en Rails debes instalar la rubygem en el gemfile de tu proyecto.

<pre><code>
gem 'bootstrap-sass', '~> 3.1.1'
gem 'autoprefixer-rails'

</code></pre>

la gema autoprefixer es opcional, agrega automáticamente los proveedores de prefijos adecuado para tu código css cuando se compila, recomiendo usarla.

luego corremos en bundle install para instalar la gema.
<pre><code>
bundle install
</code></pre>

<hr>
2. importar los  CSS assets

vamos al archivo app/assets/stylesheets/application.css y lo renombramos como app/assets/stylesheets/application.css.sass  y añadimos a este archivo los imports.

<pre><code>
// app/assets/stylesheets/application.css.sass

@import "bootstrap-sprockets"
@import "bootstrap"
</code></pre>
<hr>
3. añadir los JS assets



abrimos el archivo app/assets/javascripts/application.js y añadimos.

<pre><code>
//= require bootstrap-sprockets
</code></pre>
ya casi esta listo!, ahora verificamos en este mismo archivo existan estos requires:
<pre><code>
//= require jquery
//= require jquery_ujs
//= require turbolinks
//= require bootstrap-sprockets
//= require_tree .
</code></pre>

es importante que require_tree este por debajo de todos los demás requires ya que este compila cada uno de los subdirectorios y archivos sobre él, de otra forma bootstrap no podría acceder a esos scripts.

<hr>
FELICIDADES!, ya has instalado y configurado adecuadamente bootstrap en tu proyecto, espero te halla funcionado y pregunta si tienes dudas, hasta pronto.
