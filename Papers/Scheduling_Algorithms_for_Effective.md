#coscheduling 
#consolidation 
#online 

[[Scheduling_Algorithms_for_Effective.pdf]]

Usa las siguientes caracteristicas para agruparlos: Scheduling of threads across processors is driven by the memory bandwidth utilization of the threads, whereas scheduling of threads within processors is driven by one of three metrics: bus transaction rate per thread, stall cycle rate per thread, or outermost level cache miss rate per thread


Este paper habla de politicas para la clasificacion de trabajos para ponerlos a trabajar en conjunto o no, segun el performance en runtime

Da como resultados un incremento del 30% (28.7%) respecto al scheduler del sistema operativo y la complexity es lineal, lo que lo hace escalable
PERO, solo consideran CPU intensive jobs, nada de comunicaciones ni IO ni archivos.

Usa contadores online. Performance monitoring, Typical events are related to the memory subsystem performance, the execution units utilization, branch predictions, resource stalls, etc.

Pagina 7, citado textualmente, razones por las:
The reason is straightforward: the performance of a multithreaded application when its threads run on different processors almost always exceeds the performance of the same
application when the same number of threads runs on different execution contexts on the same processor. Contention for shared resources limits efficiency dramatically on current commercial multithreaded processors.

Pagina 9, antes de related work
The results suggest that by carefully selecting the co-scheduled threads and
pairing them on physical processors, it is possible not only
to reduce the average execution time of the workload but, at
the same time, to improve the performance of each individual application.

 Symbiotic job scheduling, 13, 14 snavely, nada, es un libro

Symbiotic job scheduling relies on sampling
the performance of different mixes of co-scheduled jobs,
using different types of performance metrics, until a consensus on the best pairing is reached. This scheduling strategy may reach optimality for certain workloads but is very
sensitive to their dynamic characteristics


Hardware mechanisms proposed to improve the quality of service to threads in terms of instruction throughput [5] (Conferencia)
The interference between threads in the shared cache has also been a focal point of investigation for multithreaded processors and chip multiprocessors [9]. (Conferencia)

Static cache partitioning: the most common technique used to alleviate thread interference is to partition the cache between processors or execution contexts [16, 17, 4, 8] (Conferencias y libros 
However dynamic schemes have also been proposed recently[8] (Libro).


-----------
Cont. (no es cont lel, no se de donde sale)

"Even if devoting the entire CMP to each application were to deliver best performance, that solution remains infeasible without as many CMPs as applications in the workload"

Corbalan et al. [7] precio de context switching
 [17, 18, 22] buscan que aplicaciones son incompatibles en paralelo, quieren reducier la contencion
Nesbit et al. [17, 18] implementa politicas que aseguran reparto de recursos
 Suleman et al. [24] bandwidth aware threads, pero que no es optimo segun indica este paper

[16] (reducing contention at all levels of memory) efecto de gang scheduling!!
Suh et al. [23], como afecta la cache en el rendimiento

 Banikazemi et al. [2] non invasive scheduler?