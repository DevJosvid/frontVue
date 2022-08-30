el projecto fue desarrollado con vue version 5.0.8, se planteo al inicio que fuera una card, sin embargo, se decidio despues que se reemplazaria por un div, se divide en dos partes, el buscador (llamado autocomplete debido a que esta es basicamente su funcion), y el spaceResults (la parte donde se despliqga los resultados).

Se opto para el consumo de la API el axios, debido a tener conocimientos previos con el ,aunque no habria ningun problema en usar fetch.

para la funcion de buscar y comparar con los resultados de la api en tiempo real, se uso un include comparando el value del autocomplete y los resultados de la api (que se guardaron en una variable llamada Fruits)