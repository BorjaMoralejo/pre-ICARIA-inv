#coscheduling 

[[Improving_Parallel_Job_Scheduling.pdf]]

Gang scheduling teniendo en cuenta IO y que esa sección de IO va cambiando junto a la ejecución del job. Este articulo tiene en cuenta los jobs que se autobloquean con IO para mantenerlos circulando en cores idles o cuando otro proceso se bloquea para conseguir mejor respuesta a esos procesos IO.

Ventajas de gang scheduling / coscheduling 16, 10, 13, 30]
10, [[Improved_Utilization_and_Responsiveness.pdf]]

20?] [[Implications_of_IO_for_Gang_Scheduled_Workloads.pdf]]]] mira las implicaciones de IO en gang schedulers

Otros gang scheduling:

Usa tres clases, communication bound, io bound y cpu bound

Traditional gang schedulers 3, 15] 
[[Implementation_of_Gang-Scheduling]]
~~Distributed hierarchical control schedulers 11, 12]~~

26?]