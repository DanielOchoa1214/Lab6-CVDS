# Lab6-CVDS

## Seting up Azure resource

Primero creamos una base de datos con los datos especificados en el tutorial enviado, con usuario sys admin y contraseña Abcdefghi1

<img width="465" alt="Screen Shot 2022-10-23 at 2 22 41 PM" src="https://user-images.githubusercontent.com/77862016/197411944-1dc19107-34a2-4084-b9b3-09fafefdac00.png">

Por lo que la configuracion basica quedo de la siguiente manera

<img width="734" alt="Screen Shot 2022-10-23 at 2 23 28 PM" src="https://user-images.githubusercontent.com/77862016/197412013-93ad7618-990a-4bb1-9bf8-5c0ac2ad3ebc.png">

<img width="698" alt="Screen Shot 2022-10-23 at 2 24 16 PM" src="https://user-images.githubusercontent.com/77862016/197412122-75af45d3-46f5-4b03-a7fe-ecc5dae19c72.png">

<img width="456" alt="Screen Shot 2022-10-23 at 2 24 57 PM" src="https://user-images.githubusercontent.com/77862016/197412277-19f543c3-ab58-4672-88f3-525049f8b1ba.png">

A luego pasamos a la seccion de AppService, en esta creamos una instancia de maquina virtual con las especificaciones dadas en el tutorial

<img width="402" alt="Screen Shot 2022-10-23 at 2 29 02 PM" src="https://user-images.githubusercontent.com/77862016/197413365-a9821a83-123a-4ed9-9687-e5e95811b04e.png">

Y luego creamos otra pero con el nombre indicando que es una maquina en produccion

<img width="401" alt="Screen Shot 2022-10-23 at 2 30 55 PM" src="https://user-images.githubusercontent.com/77862016/197413782-3c5d6728-fed9-4152-80de-b3dd7305bd6b.png">

Luego vamos a la configuracion de los grupos de recursos y le damos click en la base de datos

<img width="759" alt="Screen Shot 2022-10-23 at 2 33 53 PM" src="https://user-images.githubusercontent.com/77862016/197414240-851d7db5-9f44-4a93-9cb9-dc01566786ff.png">

Intentamos cambiar la opcion de permitir que Azure accediera al servidor pero al parcer por algun tipo de actualizacion no esta disponible, por lo que continuamos y esperamos que no nos afecte en el futuro

<img width="759" alt="Screen Shot 2022-10-23 at 2 42 57 PM" src="https://user-images.githubusercontent.com/77862016/197414528-5df9bcf5-0d4e-427f-a5cc-b607a0bd004f.png">

## Create a continuous release to the QA stage

Antes de poder empezar con esta seccion debemos crear una organizacion en Azure, con el nombre Parts Unlimited y luego entramos en el Azure DevOps y empezamos a crear el pipeline

![Screen Shot 2022-10-26 at 7 05 02 PM](https://user-images.githubusercontent.com/77862016/198161076-c510bcfa-c507-4218-b5b4-a75b01efd46b.png)

Luego eliminamos el pipeline que ya estaba creado anteriormente para crear el que nos dice el tutorial y este fue el resultado final

![Screen Shot 2022-10-26 at 7 28 31 PM](https://user-images.githubusercontent.com/77862016/198163371-af3471c5-f8c4-4b45-9658-96b48c8f7895.png)

## Configuring the Azure app services

En esta seccion empezamos linkeando la base de datos con las  2 aplicaciones web creada anteriormente

![Screen Shot 2022-10-26 at 7 31 46 PM](https://user-images.githubusercontent.com/77862016/198163706-feeeb52b-1387-4191-9af8-8f00a76fd85d.png)

## Invoking a continuous delivery release to QA

Empezamos editando el archivo Layaout.cshtml

![Screen Shot 2022-10-26 at 7 38 33 PM](https://user-images.githubusercontent.com/77862016/198164290-9f470286-d9ab-44d6-8e50-f664d221357b.png)

Pero antes de lograr que funcionen los cambios debemos pedir permisos de paralelismo para lo cual debemos esperar unos dias

![Screen Shot 2022-10-26 at 7 43 01 PM](https://user-images.githubusercontent.com/77862016/198164879-92223f4e-9ee0-4195-86d3-d3424c555fd6.png)
