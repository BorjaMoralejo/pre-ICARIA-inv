Hacer una prueba con RAPL y ver el consumo de una aplicación singled threaded, hacer la prueba con la aplicación de SCP en serie y analizar el consumo de los cores de mi portatil. Si no se puede, pues solo el socket. Lo que intento conseguir con esto es encontrar la variabilidad de los cores, por muy pequeño que sea.

Primero voy a planificar lo que voy a hacer

Cada punto se considera terminado cuando se haya documentado al menos un poco. Cada fichero de objetivo se considera terminado cuando se haya documentado bien lo que ha ocurrido.

[[RAPL_Consumo]]

Luego puedo empezar con un programa profiler para determinar la naturaleza de la aplicacion. Por ejemplo, si ha sido cpu intensive, los cache misses, el uso de memoria, I/O... Me he encontrado articulos que lo han hecho y tienen referencias.

[[RAPL_Profiler]]


Empezar con el plugin de slurm que de primeras colocará tareas segun el nombre que tengan los hilos o algo asi simple. Para ello se usara el funcionamiento de simulador que tiene slurm. 


Esperar a la decisión que se va a tomar para investigar

