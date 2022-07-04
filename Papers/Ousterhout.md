#coscheduling 

[[Ousterhout.pdf]]

El origen de coscheduling y la matriz de ousterhout, una matriz con procesos por columnas y tiempos (tiempo de proceso) por fila. Se utiliza al coschedulear.
Luego hay otra forma, la continua, en vez de usar una matriz utiliza una secuencia pero mueve la ventana de scheduling, reduciendo la fragmentacion interna pero aumentando la externa.
Al final la matriz da mejores resultados.

El coscheduling intenta reducir el trashing y el numero de veces que ocurre cambio de contexto. Los procesos inactivos se mantienen un rato en el procesador bloqueados hasta que pasa el tiempo y si noh an recibido nada, se sacan y se cambian por otros.
