PROYECTO INDIVIDUAL ML
=============


### OBJETIVO

- Presentar y explicar en un archivo de texto de fácil acceso el propósito del proyecto, con información sobre cómo hacer una prediccion con machine learning.
- Escoger un modelo que tenga una mejor accuary y recall para poder a proceder a hacer la prediccion

## Resumen

-En el repositorio hay dos modelos de prediccion en la version 1.0 los datos usados son mas pesados, por lo cual al momento de realizar el ajuste el tiempo de demora es altisimo por la cantidad de datos que se tiene y lo pesado del archivo la prediccion es alta al comparar con los resultados reales accuary = 0.93 y un recall = 0.94, en la  segunda version se hizo un poco menos pesado aunque tambien toma su tiempo en escoger el mejor modelo con el GridSearchCV que si bien toma su tiempo te da los mejores parametros para poder ajustar el modelo en la version 2.0 sale el accuary= 0.91 y un rcall= 0.82 comparado con la primera version es menos pesada pero tiene un mejor accuary que es lo que se busca al momento de realizar una prediccion.

## Métrica a utilizar
​
Como método de evaluación del desempeño, dependerá del modelo que usted decida implementar.
​
1. Para el modelo de aprendizaje supervisado, se utilizará la métrica `Accuracy` para las propiedades de precio bajo (low) a partir de la matriz de confusión (Confusion Matrix).

$$ Accuracy=\frac{TP+TN}{P+N}$$

siendo $TP$ los verdaderos positivos (las propiedades de precio 'low' que realmente lo son), $TN$ verdaderos negativos (las propiedades que realmente NO son de precio 'low') y $P+N$ población total.

Como métrica adicional para verificar el desempeño de su modelo, también se utilizará la métrica de precisión (Recall) para las propiedades baratas.

$$ Recall=\frac{TP}{TP+FN}$$

​
Donde $TP$ son los verdaderos positivos (las propiedades de precio 'low' que realmente lo son) y $FN$ los falsos negativos (las propiedades de precio 'low' que fueron marcadas incorrectamente).

## Transformacion de datos

- En la primera version se hara uso del codigo onehotencoder para poder usar las categorias como codigos binarios y pasar a usarlos como caracteristicas del modelo para hacer la prediccion con un mejor accuary.
- se crea en los datos de entrenamiento una columna 'category_price' donde discretizamos los valores de 'price' en 'low', 'medium', 'high' luego se crea transforma los datos en codigo binario en el cual se usa como principal valor 'low' y asi poder hacer la prediccion de los datos de testeo si un 'price' es 'low' o no.

## Archivos provistos
​
Se proveen los siguientes archivos en formato parquet:
 - 'train.parquet': Contiene 346479 registros y 22 dimensiones, el cual incluye la información **numérica** del precio en la columna `price`.
 - 'test.csv': Contiene 38498 registros y 21 dimensiones, el cual no incluye la información del precio. 

 Link al dataset: https://drive.google.com/drive/folders/1nJ9ZMj6E6zh6McC9NwCA6KopfUIOG_1O
 
 ## Descripción de las dimensiones
- id: Identificador del anuncio. 
- url: Link web del anuncio.
- region: Región de Estados Unidos en donde se encuentra la propiedad.
- region_url: Link web de los anuncios pertenecientes a la región. 
- price: Precio de la propiedad en dólares.
- type: Tipo de propiedad.
- sqfeet: Metros cuadrados de la propiedad.
- beds: Cantidad de dormitorios.
- baths: Cantidad de baños.
- cats_allowed: Si se permiten gatos en la propiedad toma el valor 1, 0 para caso contrario.
- dogs_allowed: Si se permiten perros en la propiedad toma el valor 1, 0 para caso contrario.
- smoking_allowed: Si se permite fumar en la propiedad toma el valor 1, 0 para caso contrario.
- wheelchair_access: Si la propiedad posee acceso para sillas de ruedas toma el valor 1, 0 para caso contrario.
- electric_vehicle_charge: Si la propiedad posee cargador para vehículos eléctricos toma el valor 1, 0 para caso contrario.
- comes_furnished: Si la propiedad viene amueblada toma el valor 1, 0 para caso contrario.
- laundry_options: Opciones de lavandería (w/d in unit: Lavadora/secadora en la propiedad, w/d hookups: conexión para lavadora/secadora, laundry on site: servicio de lavandería en el lugar, laundry in bldg: servicio de lavandería en el edificio, no laundry on sit: sin servicio de lavandería).
- parking_options: Opciones de estacionamiento (off-street parking: zona de estacionamiento, attached garage: garaje incluido, carport: cochera/garaje abierto, detached garage: garaje separado, street parking: estacionamiento delimitado en la calle, no parking: sin estacionamiento, valet parking: estacionamiento con servicio valet).
- image_url: Link web de la imagen de la propiedad en el anuncio. 
- description: Descripción de la propiedad puesta en el anuncio. 
- lat: Latitud.
- long: Longitud.
- state: Código del estado al que pertenece la propiedad.


###End
