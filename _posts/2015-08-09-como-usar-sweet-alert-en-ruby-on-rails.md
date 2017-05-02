---
layout:     post
title:      como usar SweetAlert en Ruby on Rails
date:       2015-08-09
summary:    usar sweet alert cob RoR
categories: jekyll

tags:
 - about
 - jekyll
---

SweetAlert es una famosa librería facil de usar que pretende reemplazar los famosos “alert” y “prompt” con versiones de un aspecto mejor que incluye animaciones y un diseño bastante bueno, puedes descargar la librería con los recursos CSS desde  [aquí](http://t4t5.github.io/sweetalert/), te recomiendo revisar las configuraciones  y metodos que son bastante amplios.



instalación:

para rails existe una gema la cual puedes encontrar aquí, puedes revisar las versiones y manos a la obra!!!

lo primero que debes hacer es añadir la gema al archivo gemfile, en este caso tengo la versión 0.0.7, pero recuerda usar la ultima que revisaste en la web de la gema en rubygems.org

<pre><code>#gema de sweetalert, alertas animadas, reemplazan alerts y prompts de js
gem 'sweet-alert', '~> 0.0.7'
</code></pre>




luego corres en consola  bundle install para instalar la gema.
Voilà!, ya puedes usar SweetAlert donde y como quieras sin tener que configurar nada ni hacer un call al fin del mundo, no es genial Rails?!


implementar:

para usar SweetAlert debes recordar que esta hecho en js, entonces deber usar las etiquetas <script>, por ejemplo.
<code>
<% if notice %>
 <script>
swal({ title: "<%= notice %>", type: "success", timer: 3000,
showConfirmButton: false, closeOnConfirm: true });
</script>
 <% end %>
</code>


esto es solo una de las muchas formas de usar SweetAlert en Ruby on Rails, si te sirvió la información recuerda darle me gusta y gracias por los comentarios.
