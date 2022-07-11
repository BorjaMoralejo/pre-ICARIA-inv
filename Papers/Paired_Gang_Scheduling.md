#coscheduling 
#consolidation 
#key (solo porque se llega a entender facil la implementación del coscheduling)


[[Paired_Gang_Scheduling]]

Combina CPU intensive con IO y blocking communication.

backfilling 13] [[backfilling_paper]]

gang scheduling 14] [[Ousterhout]]

Relaxations of gang scheduling (subtipos) 11, 7, 22, 1] 
11: [[Implications_of_IO_for_Gang_Scheduled_Workloads]]
7:Flexible coscheduling [[Flexible_coscheduling_mitigating]]


Overlap de CPU e IO eficiente 16] The Impact of I/O on Program Behavior and Parallel Scheduling

Centralized gang scheduler 4, 9, 5, 8]

9, [[Implementation_of_Gang-Scheduling]]

Clasificando CPU y recursos 19] y 18] formula

19, [[Improving_Parallel_Job_Scheduling]]

Este articulo tiene una forma de predecir el uso en base al historial, aunque no demasiado detallado (creo que esta en 19]).

La aplicación del workload es una que simula el comportamiento, no es una benchmark. Aunque luego usan QCRD que tiene diferentes fases, sacada de 15]


Slowdown es calculado de la siguiente manera:

## $\frac{1}{N}\sum_{i=1}^{N}\frac{t_{Elapsed_{i}}}{t_{Executing_{i}}}$
Donde N es el número de jobs, $t_{Executing_{i}}$ es el tiempo de ejecución del job $i$ y $t_{Elapsed_{i}}$ es el tiempo total del job, el tiempo de respuesta se obtiene haciendo la media de $t_{Elapsed}$.

Se fija si ocurre un cambio en la relación de CPU o IO, y ejecuta los jobs por separado para estimar la nueva fase de la tarea. Dice que un cambio que determina la aislacion es un cambio en la CPU del 20%. Hacer la aislación para analizar el verdadero uso de CPU e IO solo dio un overhead de 1%