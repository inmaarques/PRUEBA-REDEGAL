
# yellow_taxi

Utilizando los datos de viajes de “Yellow Taxi” de NYC, creamos una aplicación que recibe como entrada la url del fichero csv con los datos mensuales disponibles, y devuelve como resultado los 10 destinos con el mayor número de viajes que, individualmente, superan el percentil 0.95 en distancia por viaje, incluyendo su distrito y su zona.


## Instalación
Hemos desarrollado esta aplicación con python 3.9, así como con las librerías numpy y pandas

Instalación python

```bash
  https://www.python.org/downloads/
```
Instalación pandas

```bash
  https://pandas.pydata.org/docs/getting_started/install.html
```
Instalación numpy

```bash
  https://numpy.org/install/
```
## Documentation

Contamos con dos tablas, la primera a la que llamamos "trip-taxi" incluye Los registros de viaje de taxi amarillo incluyen campos que capturan las fechas/horas de recogida y entrega, lugares de recogida y entrega, distancias de viaje, tarifas detalladas, tipos de tarifas, tipos de pago y recuentos de pasajeros informados por el conductor.
La segunda, llamada "taxi_zone" es una tabla de búsqueda por zonas mediante un identificador ID, que nos indica tanto el distrito como la zona.
- Una vez leídos los archivos csv mediante el acceso a su url, los convertimos en DataFrame para facilitar su limpieza y tratamiento. 
- Estudiamos las columnas y los tipos de datos que contienen en ambas tablas
- Nos centramos en la limpieza de datos de df_trip_taxi, quedándonos solamente con las columnas que vamos a necesitar: "trip_distance" y "DOLocation"
  "trip_distance" nos indica la distancia del viaje realizado y, "DOLocationID" el ID de la localización del fin del trayecto del cliente.
- Comprobamos la existencia de nulos
- Nos quedamos con los valores que se encuentran por encima del percentil 95 con respecto a la distancia de viaje
- Agrupamos por número de viajes por destino y los ordenamos de forma descendente
- Nos quedamos con los 10 primeros datos
- Añadimos las columnas "end_boroug" y "end_zone" vacías, para luego rellenarlas con los datos de la tabla df_taxi_zone
- Creamos una función para buscar la localización a través del locationID en el dataFrame df_taxi_zone
- Iteramos la columna "DOLocationID" de "df_trip_taxi" para obtener sus localizaciones ("Zone" y "Borough") con el metodo "search_location_by_locationId" y persistirlas en "df_trip_tax
- Eliminamos la columna "DOLocationID" para que el DataFrame se ajuste a lo solicitado.



## Screenshots

Ejemplo de resultado

<img width="342" alt="image" src="https://user-images.githubusercontent.com/93014385/149304525-b6408311-6051-48fe-ba23-efa81ff72700.png">



