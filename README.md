# Lab6-CVDS

## Autores:
- Wilmer Arley Rodriguez Ropero
- Daniel Sebastian Ochoa Urrego

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

Y con los permisos ya el pipeline funciona

![Screen Shot 2022-10-27 at 4 22 15 PM](https://user-images.githubusercontent.com/77862016/198400832-c493e132-7f37-4983-988f-b30bfa0e6b78.png)

Y al entrar al link [de la pagina](https://laboratorio6ciclos-qa.azurewebsites.net) podemos ver lo siguiente

![Screen Shot 2022-10-27 at 4 39 02 PM](https://user-images.githubusercontent.com/77862016/198403525-1d35edb3-aeba-4067-aec5-16818fc63d27.png)

## Creating a gated release to the production stage

Para esta parte primero editamos el release del pipeline como especifica el tutorial

![Screen Shot 2022-10-27 at 4 46 19 PM](https://user-images.githubusercontent.com/77862016/198404458-166ca40f-7e1a-4d47-9bc6-e1687a626576.png)

Luego modificamos los queries como espesifica el laboratorio

![Screen Shot 2022-10-27 at 4 48 10 PM](https://user-images.githubusercontent.com/77862016/198404718-aa956551-5a54-4539-95ac-fde36f3e553e.png)

Y mabiamos el nombre de la etapa clonada por Prod y configuramos cre la misma manera que la anterior con las especificaciones dadas en el tutorial

![Screen Shot 2022-10-27 at 5 02 01 PM](https://user-images.githubusercontent.com/77862016/198406640-bdbd6525-c6c5-4f31-8d9b-91b2ac102b77.png)

Y actualizamos el chtml por la nueva version que realizamos 

![Screen Shot 2022-10-27 at 5 04 00 PM](https://user-images.githubusercontent.com/77862016/198406872-8522391d-9921-4deb-9cb5-e3fb96278709.png)

Y al desplegar la aiplicacion mientras pasa por el pipe line fallara pues uno de los quality gates no se esta cumpliendo

![Screen Shot 2022-10-27 at 5 06 21 PM](https://user-images.githubusercontent.com/77862016/198407172-abad0f14-c842-4e64-9558-3363259cd825.png)
![Screen Shot 2022-10-27 at 5 06 35 PM](https://user-images.githubusercontent.com/77862016/198407181-f5454087-77a6-46b4-b3f7-0248eeb03c11.png)

Luego seguimos los pasos del tutorial para arreglarlo

![Screen Shot 2022-10-27 at 5 42 28 PM](https://user-images.githubusercontent.com/77862016/198411583-f3a47729-c775-4ed7-a84a-24807a7d4711.png)

Y luego aprovamos el paso a produccion

![Screen Shot 2022-10-27 at 6 02 58 PM](https://user-images.githubusercontent.com/77862016/198413855-fbbedb83-a467-44b0-90df-3d42a008a91f.png)
![Screen Shot 2022-10-27 at 6 05 00 PM](https://user-images.githubusercontent.com/77862016/198414060-d62693db-5050-461b-8860-4c14750b79f6.png)

Y ingresamos a la pagina de produccion

![Screen Shot 2022-10-27 at 6 05 33 PM](https://user-images.githubusercontent.com/77862016/198414127-d975cc3a-efd8-4a88-9cda-e246034824a6.png)

## Working with deployment slots

Vamos a la seccion de slots de de desplieque y agregamos uno

![Screen Shot 2022-10-27 at 6 06 44 PM](https://user-images.githubusercontent.com/77862016/198414224-ea40e69e-e43d-4e4b-bf97-66d5840c294f.png)

Volvemos al DevOps y agregamos el slot creado en la etapa de produccion

![Screen Shot 2022-10-27 at 6 09 30 PM](https://user-images.githubusercontent.com/77862016/198414510-96553409-5633-4163-b232-7dafea075cef.png)

Luego cambiamos la verion de la pagina otra vez y guardamos los cambios

![Screen Shot 2022-10-27 at 6 10 47 PM](https://user-images.githubusercontent.com/77862016/198414638-91624acc-39c6-4145-bea1-439760215aee.png)

Luego saldra otro release y lo desplegamos

![Screen Shot 2022-10-27 at 6 15 06 PM](https://user-images.githubusercontent.com/77862016/198415044-61578f22-edd3-474b-acb1-abf36a0bb4f9.png)

Y revisamos la pagina en el browser y deberia quedar igual

![Screen Shot 2022-10-27 at 6 15 41 PM](https://user-images.githubusercontent.com/77862016/198415122-51ade0b0-4adb-4b81-85ea-96d8ea592017.png)

Y cuando cambiamos la URL y le agregamos el staging en esta veremos la actualizacion 

![Screen Shot 2022-10-27 at 6 16 39 PM](https://user-images.githubusercontent.com/77862016/198415184-e33f4217-4f31-4704-b314-f6f4c62c2b20.png)

Luego para arreglar esto volvemos al portal le damos la opcion de swap y revisamos que la pagina este actualizada con el link normal

![Screen Shot 2022-10-27 at 6 21 08 PM](https://user-images.githubusercontent.com/77862016/198415610-a5566aeb-600e-4528-bc83-7ea2511106ba.png)

[URL del sitio desplegado](https://laboratorio6ciclos-prod.azurewebsites.net)
