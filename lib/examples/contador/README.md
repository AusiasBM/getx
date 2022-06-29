# Contador con GetX
---

## MAIN

El primer paso es agregar GetMaterialApp a nuestro main, esto solo nos hace falta si vamos a utilizar:

* Rutas
* Snackbars
* internacionalización
* bottomSheets
* dialogos
* APIs de alto nivel relacionada con rutas
* Ausencia de contexto


## Controlador

En el controlador vamos a crear su clase con la lógica de negocio colocando todas las variables, métodos y controladores dentro de ella. 

Puede hacer que cualquier variable sea observable usando un simple ".obs".


## Vista

Creamos la vista, usando StatelessWidget y de esta forma ahorramos **RAM**, con **GetX** ya **no** hace falta utilizar StatefulWidgets.

### Añadir Controlador en GetX
Para que podamos utilizar las variables obs en la vista tenemos que añadir el controlador en alguna parte de nuestro código. 
`final Controller c = Get.put(Controller());`
Luego que lo hayamos añadido ya podremos utilizarlo en cualquier parte de la aplicaicón.

Si nos encontramos en el mismo widget que lo hemos añadido, no hace falte hacer nada más, en caso de que estemos en un widget distinto tenemos que buscar ese controlador en GetX.
`final Controller c = Get.find();`
`c.count.string`
Lo que hemos hecho es crear un buscador y luego buscar la variable count dentro de los controladores que tiene guardados GetX.


### Obx
Si utilizamos **Obx** `Obx(() => Text("Clicks: " + c.count.string))` y dentro ponemos una variable **obs** `c.count.string`, estamos haciendo que cuando se actualize la variable obs, se actualize la vista Obx. 

En caso de que **NO** queramos que se actualize la vista, nos vale solo con poner la variable obs `c.count.string`. Este caso nos será utili para cuando mostremos información en una página que sea de información y que solo queramos que se actualize al entrar.

## Conclusión

Este es un proyecto simple pero ya deja en claro cuán poderoso es GetX. A medida que su proyecto crezca, esta diferencia se volverá más significativa. GetX fue diseñado para trabajar con equipos, pero también simplifica el trabajo de un desarrollador individual. Mejore sus plazos, entregue todo a tiempo, sin perder rendimiento. GetX no es para todos, pero si te identificaste con esa frase, ¡GET es para ti!






