#                             *Trabajo SQL*

#### 1 PUNTO

- Lista el nombre de todos los productos que hay en la tabla producto. 

  ```sql
  SELECT  p.nombre
  FROM producto as p;
  ```

- Lista los nombres y los precios de todos los productos de la tabla producto.

  ```sql
  SELECT p.nombre, p.precio                                            
  FROM producto as p;
  ```

- Lista todas las columnas de la tabla producto.

  ```sql
  SELECT p.codigo, p.nombre, p.precio, p.codigo_fabricante
  FROM producto as p;
  ```

- Lista el nombre de los productos, el precio en euros y el precio en dólares
estadounidenses (USD).

  ```sql
  SELECT p.nombre, p.precio, (p.precio*1.06) as dolares
  FROM producto as p;
  ```

- Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD). Utiliza los siguientes alias para las columnas: nombre de producto, euros, dólares.

  ```sql
  SELECT p.nombre as nombre de producto, (p.precio*1.06) as dolares       
  (p.precio*1.09) as euros
  FROM producto as p;
  ```

- Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a mayúscula.

  ```sql
  SELECT UPPER(p.nombre) as nombre, precio
  FROM producto as p;
  ```

- Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a minúscula.

  ```sql
  SELECT LOWER(p.nombre) as nombre, precio
  FROM producto as p;
  ```

- Lista el nombre de todos los fabricantes en una columna, y en otra columna obtenga en mayúsculas los dos primeros caracteres del nombre del
fabricante.

  ```sql
  SELECT f.nombre, UPPER(SUBSTR(f.nombre, 1, 2))
  FROM producto as p;
  ```

- Lista los nombres y los precios de todos los productos de la tabla producto, redondeando el valor del precio.

  ```sql  
  SELECT p.nombre, ROUND(p.precio)
  FROM producto as p;
  ```

- Lista los nombres y los precios de todos los productos de la tabla producto, truncando el valor del precio para mostrarlo sin ninguna cifra decimal.

  ```sql  
  SELECT p.nombre, CAST(p.precio as INT) as precio_truncado
  FROM producto as p;
  ```

- Lista el identificador de los fabricantes que tienen productos en la
tabla producto.

  ```sql  
  SELECT p.codigo_fabricante
  FROM producto as p;
  ```

- Lista el identificador de los fabricantes que tienen productos en la
tabla producto, eliminando los identificadores que aparecen repetidos.

  ```sql  
  SELECT DISTINCT p.codigo_fabricante
  FROM producto as p;
  ```

- Lista los nombres de los fabricantes ordenados de forma ascendente.

  ```sql  
  SELECT f.nombre
  FROM fabricante as f
  ORDER BY f.nombre ASC; 
  ```

- Lista los nombres de los fabricantes ordenados de forma descendente.

  ```sql  
  SELECT f.nombre
  FROM fabricante as f
  ORDER BY f.nombre DESC; 
  ```

- Lista los nombres de los productos ordenados en primer lugar por el
nombre de forma ascendente y en segundo lugar por el precio de forma
descendente.

  ```sql  
  SELECT p.nombre, p.precio
  FROM producto as p
  ORDER BY p.nombre ASC, p.precio DESC; 
  ```

- Devuelve una lista con las 5 primeras filas de la tabla fabricante.

  ```sql  
  SELECT *
  FROM fabricante
  LIMIT 2 OFFSET 3; 
  ```

- Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante. La cuarta fila también se debe incluir en la respuesta.

  ```sql  
  SELECT p.nombre, p.precio
  FROM producto as p
  ORDER BY p.precio ASC
  LIMIT 1; 
  ```

- Lista el nombre y el precio del producto más barato. (Utilice solamente las cláusulas ORDER BY y LIMIT)

  ```sql  
  SELECT p.nombre, p.precio
  FROM producto as p
  ORDER BY p.precio DESC
  LIMIT 1; 
  ```

- Lista el nombre y el precio del producto más caro. (Utilice solamente las cláusulas ORDER BY y LIMIT)

  ```sql  
  SELECT p.nombre, p.precio
  FROM producto as p
  ORDER BY p.precio ASC
  LIMIT 1; 
  ```

- Lista el nombre de todos los productos del fabricante cuyo identificador de fabricante es igual a 2.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.codigo_fabricante = 2;
  ```

- Lista el nombre de los productos que tienen un precio menor o igual a 120€.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.precio <= 120;
  ```
- Lista el nombre de los productos que tienen un precio mayor o igual a 400€.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.precio >= 400;
  ```

- Lista el nombre de los productos que no tienen un precio mayor o igual a
400€.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.precio < 400;
  ```

- Lista todos los productos que tengan un precio entre 80€ y 300€. Sin utilizar el operador BETWEEN.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.precio >= 80 AND p.precio <= 300;
  ```

- Lista todos los productos que tengan un precio entre 60€ y 200€. Utilizando el operador BETWEEN.

  ```sql  
  SELECT p.nombre
  FROM producto as p 
  WHERE p.precio BETWEEN 60 AND 200;
  ```

- Lista todos los productos que tengan un precio mayor que 200€ y que el
identificador de fabricante sea igual a 6.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.precio > 200 AND codigo_fabricante = 6;
  ```

- Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Sin utilizar el operador IN.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE codigo_fabricante = 1 OR codigo_fabricante = 3 OR codigo_fabricante   = 5;

  ```

- Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Utilizando el operador IN.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE codigo_fabricante IN(1, 3, 5);
  ```

- Lista el nombre y el precio de los productos en céntimos (Habrá que
multiplicar por 100 el valor del precio). Cree un alias para la columna que
contiene el precio que se llame céntimos.

  ```sql  
  SELECT p.nombre, p.precio * 100 AS centimos
  FROM producto as p;
  ```

- Lista los nombres de los fabricantes cuyo nombre empiece por la letra S.

  ```sql  
  SELECT f.nombre
  FROM fabricante as f
  WHERE f.nombre LIKE 'S%';
  ```

- Lista los nombres de los fabricantes cuyo nombre termine por la vocal e.

  ```sql  
  SELECT f.nombre
  FROM fabricante as f
  WHERE f.nombre LIKE '%e';
  ```

- Lista los nombres de los fabricantes cuyo nombre contenga el carácter w.

  ```sql  
  SELECT f.nombre
  FROM fabricante as f
  WHERE f.nombre LIKE '%w%';
  ```

- Lista los nombres de los fabricantes cuyo nombre sea de 4 caracteres.

  ```sql  
  SELECT f.nombre
  FROM fabricante as f
  WHERE LENGTH(f.nombre) = 4;
  ```

- Devuelve una lista con el nombre de todos los productos que contienen la
cadena Portátil en el nombre.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.nombre LIKE '%Portatil%'; 
  ```

- Devuelve una lista con el nombre de todos los productos que contienen la
cadena Monitor en el nombre y tienen un precio inferior a 215 €.

  ```sql  
  SELECT p.nombre
  FROM producto as p
  WHERE p.nombre LIKE '%Monitor%' AND p.precio < 215; 
  ```

- Lista el nombre y el precio de todos los productos que tengan un precio
mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en
orden descendente) y en segundo lugar por el nombre (en orden
ascendente).

  ```sql  
  SELECT p.nombre, p.precio
  FROM producto as p
  WHERE p.precio >= 180
  ORDER BY p.precio DESC, p,nombre ASC; 
  ```


  #### 2 PUNTO, CONSULTAS MULTITABLA

- Devuelve una lista con el nombre del producto, precio y nombre de
fabricante de todos los productos de la base de datos.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo;
  ```

- Devuelve una lista con el nombre del producto, precio y nombre de
fabricante de todos los productos de la base de datos. Ordene el resultado
por el nombre del fabricante, por orden alfabético.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo
  ORDER BY fabricante.nombre;
  ```

- Devuelve una lista con el identificador del producto, nombre del producto,
identificador del fabricante y nombre del fabricante, de todos los productos
de la base de datos.

  ```sql  
  SELECT producto.codigo, producto.nombre, fabricante.codigo,       
  fabricante.nombre
  FROM producto, fabricante;
  WHERE producto.codigo_fabricante = fabricante.codigo;
  ```

- Devuelve el nombre del producto, su precio y el nombre de su fabricante,
del producto más barato.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo
  ORDER BY producto.precio ASC
  LIMIT 1;
  ```

- Devuelve el nombre del producto, su precio y el nombre de su fabricante,
del producto más caro.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo
  ORDER BY producto.precio DESC
  LIMIT 1;
  ```

- Devuelve una lista de todos los productos del fabricante Lenovo.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo AND   
  fabricante.nombre = 'Lenovo';
  ```

- Devuelve una lista de todos los productos del fabricante Crucial que tengan un precio mayor que 200€.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo AND   
  fabricante.nombre = 'Crucial' AND producto.precio > 200;
  ```


- Devuelve un listado con todos los productos de los
fabricantes Asus, Hewlett-Packardy Seagate. Sin utilizar el operador IN.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo AND   
  (fabricante.nombre = 'Asus' OR fabricante.nombre = 'Hewlett-Packard' OR   
  fabricante.nombre = 'Seagate');
  ```

- Devuelve un listado con todos los productos de los
fabricantes Asus, Hewlett-Packardy Seagate. Utilizando el operador IN.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo AND   
  fabricante.nombre IN ('Asus', 'Hewlett-Packard', 'Seagate');
  ```

- Devuelve un listado con el nombre y el precio de todos los productos de los fabricantes cuyo nombre termine por la vocal e.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo AND   
  fabricante.nombre LIKE '%e';
  ```

- Devuelve un listado con el nombre y el precio de todos los productos cuyo
nombre de fabricante contenga el carácter w en su nombre.

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo AND   
  fabricante.nombre LIKE '%w%';
  ```

- Devuelve un listado con el nombre de producto, precio y nombre de
fabricante, de todos los productos que tengan un precio mayor o igual a
180€. Ordene el resultado en primer lugar por el precio (en orden
descendente) y en segundo lugar por el nombre (en orden ascendente)

  ```sql  
  SELECT producto.nombre, producto.precio, fabricante.nombre
  FROM producto, fabricante
  WHERE producto.codigo_fabricante = fabricante.codigo AND producto.precio    >= 180
  ORDER BY producto.precio DESC, producto.nombre ASC;
  ```

- Devuelve un listado con el identificador y el nombre de fabricante,
solamente de aquellos fabricantes que tienen productos asociados en la
base de datos.

  ```sql  
  SELECT fabricante.codigo, fabricante.nombre
  FROM fabricante
  WHERE fabricante.codigo IN (SELECT DISTINCT codigo_fabricante FROM   
  producto);
  ```
