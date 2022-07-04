#coscheduling 

[[Adaptive_parallel_job_scheduling_with_flexible_cos.pdf]]


Adaptive_parallel_job_scheduling_with_flexible_cos, util, es algo totalmente relacionado con HPC y coscheduling, pero por alguna razon no me ha inspirado confianza, quizas por la frase de: se han tomado las mejores mediciones. Su scheduler pilla datos, los analiza y luego clasifica y segun la clasificacion hace acciones como darles prioridad o que sean preemtivos.



5] es un libro, causas de baja eficiencia, resource utilization , load imbalance
20], algo de network, fuera del area de investigacion de coscheduling, efecto malo por esperar a otros hilos



formas de coschedulear Implicit Coscheduling (ICS) 3], Dynamic Coscheduling (DCS) 21], Coordinated Coscheduling (CC) 4], These algorithms are distinguished by where the coordination is inferred: at sender side, receiver, or both, espectively.

Load imbalance has three main sources: application imbalance, workload imbalance, and heterogeneity of hardware resources.

Es de un libro, como mucho sacarlo del propio doc pero tampoco es que importe esta clasificación ya que de todos los otros papers que he leido no se ha mencionado, Clasificacion de trabajos, 14] 24]

----------------
Cont.

Que es gang scheduling: 9]

Ousterhout matrix [[Ousterhout]]
Efectos de coscheduling 6 7]

