#coscheduling 
#consolidation 
#long 


[[Contention-Aware_Scheduling.pdf]]

Comentan que la cache no es la principal fuente de degradación, memory controller contention, memory bus contention y prefetching hardware contention se combinan para crear esa degradación.

Origen de Distributed Intensity

DIO tiene dos partes, un clasificador en el que se puede llegar a meter la IA y un seleccionador de políticas para colocarlo.

Se comparan la degradación que ocurrirá si lo combinan con otros (aunque este cálculo es caro y se hace offline) y la degradación respecto a lanzarlo individualmente.

SDC algorithm para determinar como van a interactuar entre si con la cache. Chandra et al. 2005], de todos modos muestra que no es demasiado bueno y que fijarse simplemente en el high miss rate es mejor que esto.

La clasificación de Pain llega a tener una degradación del 1%, no creo que se pueda mejorar.

El reparto que hace con las tareas es la siguiente: reparte homogeneamente los programas para que haya un missrate de cache parecido en cada nodo.

Este y [[A_Practical_Method_for_Estimating_Performance]] conluyen diciendo que no es el miss rate lo que más degrada, pero sí que es un indicador de que va a ocurrir degradación. Esto es por el uso de los controladores de memoria y la contención en el bus.

El power aware DI, DIO-POWER es un scheduler que combina los que tienen poca miss-rate juntos y los que tienen mucha los separa porque si los junta el tiempo de ejecución sube.

