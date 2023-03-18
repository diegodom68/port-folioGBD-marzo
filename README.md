# PORTFOLIO GBD
## Resumen
Esta evaluación se ha basado en el apartado DQL, que trata sobre las consultas a la base de datos. Empezamos con las consultas sobre una sola tabla y la explicación de como funcionan los select con las columnas y su tabla. Cuando ya aprendimos el funcionamiento básico de estos *select* pasamos a aprender el manejo de funcione, fechas,null y las /expresiones regulares. Esta parte era un poco nueva para mi. Vimos que lo más importante es saber trabajar con los datos para hacer una consulta exacta.Tipos de funciones, que las mas importantes son las funciones numéricas, funciones de conversion y el manejo de conversión y utilización de fechas.
Cuando vimos estos apartados, entramos en profundidad con las expresiones regulares, ya que es un apartado muy importante en estos temas. Existen 5 expresiones regulares muy importantes:
* REGEXP_LIKE
* REGEXP_SUBSTR
* REGEXP_INSTR
* REGEXP_COUNT
* REGEXP_REPLACE

Para hacer consultas un poco mas avanzadas es necesario este tipo de instrucciones. Las expresiones son tan buenas gracias a la posibilidad del uso de caracteres y simbolos en ellas. Este tema comprendia solo consultas sobre una tablas, pero hemos visto la posibilidad de hacer consultas sobre más de una tabla. En este apartado las consultas se van pareciendo más a las que podría hacer un gestor de base de datos. La palabra clave en este tema va a ser **JOIN**, ya que esta se usa para poder introducirnos en las demás tablas. Existen varios tipos de *join*.
* Natural Join, 
* Join on/using
* Cross Join.

Para introducirnos en las otras tablas necesitamos que estén conectadas entre ellas,es decir, que tengan un PK y FK
![](https://raw.githubusercontent.com/diegodom68/port-folioGBD-marzo/main/Portfolio/clases.jpg)

Como vemos en este esquema de una base de datos real, las tablas están relacionadas entre sí. Explicacion de cuando usar cada join:
* Natural -->   Cuando en dos tablas tenemos **solo** dos columnas con este nombre. Una en cada tabla. Si tenemos dos columnas en cada tabla que coincidan ya no podremos usarlo.
* Join on --> Para cuando dos tablas estan referenciadas pero el nombre de la columna es distinto entonces dentro del on (nombre1=nombre2)
* Join using --> Cuando hay en una tabla dos columnas con el mismo nombre pero si hay mas de una referencia, especificamos que referencia queremos usar.
* Cross Join --> Se utiliza para hacer comparaciones horizontales, se traduce como producto cruzado. 

Estos join solo sacan datos que cumplan estas referencias(join) pero en el caso de querer sacar tambien los datos que no la cumplan se utilizan *Outer Joins*. Cuando ya manejas todo este tipo de consultas, se pasa a ver las agrupaciones (Group By), que se utiliza en consulta de totales. Pero esto se ve en los siguientes temas.
## Reflexiones Personales
En estos temas se ha dado un avance en la materia muy importante. Ya que cada vez nos acercamos más a las consultas que hace un gestor de una base de datos, y nos acercamos más a las consultas del mundo laboral. Creo que este tema en general ha sido muy positivo para el concimiento sobre una base de datos, si que es verdad qué en las consultas hay muchas cosas que es muy dificil saberse de memoria. Todos los caracteres y símbolos de las expresiones regulares es practicamente imposible saberse todos con certeza, eso podría ser un punto negativo del tema. Pero en general creo que tiene cosas más positivas que negativas.
## Ejercicios Significativos
![](https://raw.githubusercontent.com/diegodom68/port-folioGBD-marzo/main/Portfolio/Ejer-geo25.jpg)

Esta consulta 25 de la práctica 18 (bd:geografía) tiene una dificultad muy elevada, pero a mi me sirvió mucho para entender el funcionamiento de los join, los group by, los totales, etc.
![](https://raw.githubusercontent.com/diegodom68/port-folioGBD-marzo/main/Portfolio/ejer10-geo.jpg)

Mostrar las provincias cuyo nombre de capital es distinto del nombre de la provincia; esta consulta me resultó muy  buena ya que se puede asemejar a la vida real.
![](https://raw.githubusercontent.com/diegodom68/port-folioGBD-marzo/main/Portfolio/ejer7-padre.jpg)

Muestra el nombre de las madres que hayan tenido hijos con padres distintos (conocidos)
![](https://raw.githubusercontent.com/diegodom68/port-folioGBD-marzo/main/Portfolio/ejer10-padre.jpg)
Mostrar el nombre (por pares) de todas las personas que son hermanos del mismo padre (aunque no lo sean de la madre).
![](https://raw.githubusercontent.com/diegodom68/port-folioGBD-marzo/main/Portfolio/ejer3-nba.jpg)
Mostrar, por pares, los nombres y ciudades de equipos que han alojado a la misma franquicia. Primeras filas (ordenado por id_franquicia, nombre de equipo y ciudad).
## Ejercicios Invencíon Propia
Ejercicios que yo inventaría para aprender sobre este tema:
1.
SELECT p.product_name, SUM(od.quantity) as total_sales
FROM order_details od, products p, orders o
WHERE od.product_id = p.product_id AND od.order_id = o.order_id AND o.order_date BETWEEN '2022-01-01' AND '2022-12-31'
GROUP BY p.product_name;
2.
SELECT s.supplier_name, p.product_name, p.units_in_stock
FROM suppliers s, products p
WHERE s.supplier_id = p.supplier_id
ORDER BY s.supplier_name;
Esta consulta combina información de dos tablas diferentes para mostrar los nombres de los productos y la cantidad de unidades en stock por proveedor. La consulta usa la cláusula "WHERE" para unir las dos tablas según el ID del proveedor, y la cláusula "ORDER BY" para ordenar los resultados alfabéticamente por nombre del proveedor.
## Conclusiones
En conclusión esta evaluación para mi ha sido muy interesante, el trabajo de ir aprendiendo poco a poco el funcionamiento de las consultas y ver que vás progresando en este tema, es algo muy gratificante. Si que es verdad que ha sido un camino costoso porque es algo que cuesta entender, pero poniendo empeño y un poco de trabajo todos los días se puede llegar a dominar este tema. Podría decir que lo que más me ha gustado ha sido las consultas de totales, porque le veo un sentido muy claro y una aplicación en casos muy concretos. Lo que menos me ha gustado podria ser la dificultad de entender y visualizar antes de ejecutar una consulta.
