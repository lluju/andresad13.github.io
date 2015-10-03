---
layout:     post
title:      como hacer un splash screen para android
date:       2015-08-09 15:31:19
author:     Leonel Alfonso

categories: java android androidstudio
thumbnail:  heart
tags:
 - java
 - android

 - android_studio
---


![splashscreen](http://cyrilmottier.com/media/2012/05/splash-screens-are-evil-dont-use-them/popular_apps_splash_screens.jpg)
<p align="justify">
<h4>
hemos visto muchas veces que las aplicaciones tienen un modo de presentarse al usuario, casi siempre lo hacen por medio de una pantalla de bienvenida mostrando el logo de la app por unos momentos, esto ayuda a cargar por debajo  algunos aspectos importante del flujo de la app mientras el usuario observa el logo o el mensaje de bienvenida, ademas de ser una practica aconsejable el usuario no desencanta del uso de la aplicación, es mas, muchas encuestas han confirmado que un splash screen le da cierto status a una aplicación, como si no fuera del montón, aunque lo sea y eso si, créeme que lo que menos nos debe interesar es hacer ese tipo de aplicaciones, entonces hoy he querido mostrar uno de los tantos modos de hacer un splash screen sencillo, usare android_studio para hacerlo de forma nativa, en futuros post usare rubymotion, pero primero lo primero, y considero lo recomendado como principal, google recomienda java para su plataforma así que tendré que hacer caso, aunque solo sea esta vez.
</h4>
</p>

<hr>

<p align="justify">
<h4>
1. bueno, no voy a hablar mucho de un paso a paso de las cosas, asumo que conoces como crear un proyecto y tienez cierta fluidez con java y android, asi que, manos a la obra.

primero cree un activity de nombre SplashScreen y voy solo a modificar el color de background del layout, pero si lo desean pueden usar imagenes, texto, un anim para mostrar un loading, etc.
añadi lo siguiente en el xml del layout SplashScreen.
</p>

``` xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent"
    android:layout_height="match_parent" tools:context=".splash"
    android:background="#ff029a00">

</RelativeLayout>
 ```

 <br>

 2. ahora nos ocupamos de la clase dedicada a la gestion de esta ativity, en esta definimos una cuenta atras usando las clases Timer y TimerTask.

``` javascript
public class splash extends ActionBarActivity {

    private static final long SPLASH_SCREEN_DELAY = 3000;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_splash);


        TimerTask task = new TimerTask() {
            @Override
            public void run() {

                // Start the next activity
                Intent mainIntent;
                mainIntent = new Intent().setClass(
                        splash.this, MainActivity.class);
                startActivity(mainIntent);

                // Close the activity so the user won't able to go back this
                // activity pressing Back button
                finish();
            }
        };

        // Simulate a long loading process on application startup.
        Timer timer = new Timer();
        timer.schedule(task, SPLASH_SCREEN_DELAY);


    }
```


<p align="justify">
<h4>

 cuando esta cuenta atras termine se desplegara otra activity, por supuesto lo primero que debemos hacer es crear una nueva activity, en mi caso tendra por nombre MainActivity.
 Teniendo esto ya podremos decir que tenemos un splash, con un tiempo de 3 segundos los cuales tu los puedes cambiar por los procesos que desees, especialmente los uso para cargar el consumo de alguna API, eso es todo, espero les sirva. 


</p>
