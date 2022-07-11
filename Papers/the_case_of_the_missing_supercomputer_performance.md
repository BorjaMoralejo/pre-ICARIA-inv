#key 
#measured 

Me gusta como esta hecho el articulo

[[the_case_of_the_missing_supercomputer_performance.pdf]]

Presenta una metodologia para analizar el rendimiento de un supercomputador.

Mira el efecto que tiene en SAGE, una aplicación de hydrodinamica. 
Llegan a detectar que el allreduce toma más tiempo de los esperado y que usando todos los cores del procesador se satura bastante.

![[Pasted image 20220706104046.png]]

Comentan que a barrier le pasa algo parecido.

Para mejorar el allreduce hacen lo siguiente: en vez de bloquearse al llegar a allreduce, primero esperan 100 microsegundos y si no ha ocurrido nada, se bloquean como lo harian normalmente. Eso da un incremento de 7.
Pero luego no se ve reflejado en la aplicación.


Un descubrimiento es que el "ruido" del sistema operativo a nivel de nodo crea patrones de irregularidades en los microbenchmarks que hace.

Crea una forma de clasificar irregularidades. Frecuencia del evento, duración del evento, distribución E, y la colocación (los nodos usados en los que ocurre) P.

Quitando el ruido si que mejora el rendimiento del sistema por un factor de 2.21, para ello quita daemons y aumenta la frecuencia de los heartbeats de los daemons imprescindibles. 

El rendimiento perdido o ganado del sistema se ve alterado por la "resonancia" de la aplicación. Hay ruido en el sistema de alta frecuencia(veces que interfiere en la ejecución) que afecta a aplicaciones de grano fino y hay ruido de baja frecuencia que afecta a los de grano grueso.