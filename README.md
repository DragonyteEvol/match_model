# match_model
modelo en Qlikview para realizar cruces en bases de datos con puntos geolocalizables.


# DESCRIPCIÒN

Este model de qlikview realiza cruce entre bases de datos con puntos geolocalizables como por ejemplo tiendas, restaurantes, colegios etc..
El modelo hace uso de varios datos como por ejemplo GPS, direcciòn, nombre del establecimiento etc ... pero lo unico necesario es la direcciòn y la ciudad pero para mas efectividad y precision se recomiendan la mayor cantidad de datos, el modelo hace uso de varias funciones matematicas como leveinshtein para calcular la similitud de los registros heversine para calcular la distancia entre puntos en base a la curva del ecuador, funciones de venn etc.. el modelo tambien reconoce casuisticas de no data para no perjudicar el porcentaje de cruce, ademas genera varios datos utiles como la posibilidad (registros que el sistema tiene mas de un 90% porciento de seguridad de match).


# TUTORIAL

1. En la pestaña <Variables> en la linea 21 remplazar "ODBC CONNECT TO //DB//" por la conneccion ODBC que usted utilice.
2. En la pestaña Read remplace la consulta sql por la consulta sql referente a su base de datos padre o base de datos local (recuerde que debe renombrar los campos
como se muestra en la consulta ya escrita, el identificador de la tabla padre debe ser llamado idEstablecimiento ejemplo "id as idEstablecimiento" y lo demas campos deben tener el prefijo master al final ejemplo Direccion as DireccionMaster).
3. En la pestaña data debe remplazar la consulta por la consulta referente a la tabla de base de datos con la que quiere hacer el match (recuerde que en la pestaña 
tutorial aparece como se deben renombrar los campos de la base cliente ejemplo "direccion as Direccion" o id as "id_tabla").
4. En la pestaña config puede configurar los parametros del match a realizar si requiere por ejemplo que en el match se realice interpolacion(en base a un punto mostrar 
los mas cercanos) debe cambiar el parametro false a true, si requiere que se depuren los duplicados de match puede activar noDuplicates en la tabla config alterando el valor a true.
5.Finalmente recargue el modelo y verifique los datos arrojados por el modelo.
