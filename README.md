# Base de Datos Zapateria
Base de Datos de una zapateria


### Creacion Base de datos
![BD Zapateria](bdzap.png "BD Zapateria")

### Creacion Tabla Fabricante
![Tabla Fabricante](tab_fabric.png "Tabla Fabricante")
![Tabla Fabricante](tab_fabric1.png "Tabla Fabricante")

### Creacion Tabla Articulo
![Tabla Articulo](tab_art.png "Tabla Articulo")
![Tabla Articulo](tab_art1.png "Tabla Articulo")

### Creacion Relacion 1 a Muchos entre Fabricante y Articulo
![Tablas no Relacionadas](nor_tab.png "Tablas no Relacionadas")
![Tablas Relacionadas](r_tab.png "Tablas Relacionadas")

### Insertando Datos de Fabricaante y Articulo
![Datos Fabricante](datos_fab.png "Datos Fabricante")
![Datos Articulos](dato_art.png "Datos Articulos")



## Consultas a la BD Zapatería


1. Obtener los nombres de los productos de la Zapateria.
`SELECT nombre FROM Articulo;`
![Consulta](consulta.png "Consulta")


2. Obtener los nombres y los precios de los productos de la Zapatería.
`SELECT nombre, precio FROM Articulo;`
![Consulta](consulta2.png "Consulta")


3. Obtener el nombre de los productos cuyo precio sea menor o igual a 50000
`SELECT nombre FROM Articulo WHERE precio<=50000;`
![Consulta](consulta3.png "Consulta")


4. Obtener todos los datos de los artículos cuyo precio esté entre 5000 y 40000 (ambas canditades incluidas)
`SELECT * FROM Articulo WHERE precio BETWEEN 5000 AND 40000;`
![Consulta](consulta4.png "Consulta")


5. Obtener el nombre y el precio de cada artículo, en dolares.
`SELECT nombre, precio/4240 AS precio FROM Articulo;` 
![Consulta](consulta5.png "Consulta")


6. Obtener el precio promedio de todos los artículos
`SELECT AVG(precio) as precio FROM Articulo;`
![Consulta](consulta6.png "Consulta")


7. Obtener el precio medio de los artículos cuyo codigo de fabricante sea 2.
`SELECT AVG(precio) as precio  FROM Articulo WHERE codigo_fab=2;`
![Consulta](consulta7.png "Consulta")


8. Obtener el número de artículos cuyo precio sea mayor o igual a 50000
`SELECT COUNT(*) as precio FROM Articulo WHERE precio >= 50000;`
![Consulta](consulta8.png "Consulta")


9. Obtener el nombre y precio de los artículos cuyo precio sea mayor o igual a 50000 y ordenarlos descendentemente por precio, y luego ascendentemente por nombre.
`SELECT nombre,precio FROM Articulo WHERE precio >= 50000 ORDER BY precio DESC;`
![Consulta](consulta9_1.png "Consulta")


`SELECT nombre,precio FROM Articulo WHERE precio >= 50000 ORDER BY nombre ASC;`
![Consulta](consulta9_2.png "Consulta")


10. Obtener un listado completo de artículos, incluyendo por cada articulo los datos del artículo y de su fabricante.
`SELECT Articulo.*, Fabricante.* FROM Fabricante INNER JOIN Articulo ON Fabricante.codigo=Articulo.codigo_fab;`
![Consulta](consulta10.png "Consulta")


11. Obtener un listado de articulos, incluyendo el nombre del articulo, su precio y el nombre de su fabricante.
`SELECT Articulo.nombre, Articulo.precio, Fabricante.nombre FROM Fabricante INNER JOIN Articulo ON Fabricante.codigo=Articulo.codigo_fab;`
![Consulta](consulta11.png "Consulta")


12. Obtener el precio medio de los productos  de cada fabricante, mostrando solo los codigos de fabricante.
`SELECT codigo_fab, AVG(precio)as precio FROM Articulo GROUP BY codigo_fab;`
![Consulta](consulta12.png "Consulta")


13. Obtener el precio medio de los productos de cada fabricante, mostrando el nombre del fabricante.
`SELECT Fabricante.nombre, AVG(Articulo.precio)as precio FROM Articulo INNER JOIN Fabricante ON Fabricante.codigo=Articulo.codigo_fab GROUP BY Fabricante.nombre;`
![Consulta](consulta13.png "Consulta")


14. Obtener el nombre de los fabricantes que ofrezcan productos cuyo precio medio sea mayor o igual a 50000
`SELECT COUNT(*) as precio FROM Articulo WHERE precio >= 50000;`
![Consulta](consulta14.png "Consulta")


15. Obtener el nombre y el precio del artículo mas barato.
`SELECT COUNT(*) as precio FROM Articulo WHERE precio >= 50000;`
![Consulta](consulta15.png "Consulta")


