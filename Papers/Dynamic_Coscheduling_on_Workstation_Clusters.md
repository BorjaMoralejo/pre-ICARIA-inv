#coscheduling 
#measured 

[[Dynamic_Coscheduling_on_Workstation_Clusters.pdf]]

Otro scheduler que se fija en la comunicación de los procesos para schedulearlos.

Otros que miran segun la comunicacion ~~17,~~ 6, 3, 16] (17 es una inv anterior de este)

6 [[Coscheduling_based_on]]
3 [[Effective_Distributed_Scheduling_of_Parallel_Workloads.pdf]] (implicit coscheduling)

Lo que hace es que si detecta que un proceso ha recibido un msg pero no esta en ejecucion, lo pone en ejecucion. (no se si mira como afecta esto a los compute bound)

Mira si estan comunicandose usando la NIC y modificando el procesador que tiene para que mire a que proceso pertenece (al proceso LWP)

No es del todo bueno el scheduler, usa synthetic workloads e incluso comentan que no consiguen fairness automaticamente, algo que es importante en un HPC.