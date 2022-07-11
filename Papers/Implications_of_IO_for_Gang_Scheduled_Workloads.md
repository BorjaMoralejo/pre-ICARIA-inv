#coscheduling 
#key 
#offline 

[[Implications_of_IO_for_Gang_Scheduled_Workloads.pdf]]
Se fija en las comunicaciones.
Comenta que los gang schedulers no flexibles acaban aumentando el tiempo de respuesta de las tareas IO bound. Para ello se hace un scheduler que determina si debe gang schedulearlos o no mirando la comunicacion de mensajes y cambiar dinamicamente.

under-utilization of disk se llama priority inversion y cpu under utilization se llama cpu fragmentation

priority inversion se puede mitigar dando prioridad a los IO bound tasks, usando el disco cuando este listo.

En scheduling se hace por todos los hilos por igual en gang scheduling.

SPLASH benchmark

El articulo al final trata de como incrementando o decrementando el quantum de los diferentes jobs (cpu bound e IO bound) afecta a su rendimiendo. Bajando io bound y aumentando cpu bound disminuye cpu fragmentation pero aumenta priority inversion, por lo que salen perdiendo los io bound. Al reves salen perdiendo io bound tambien por cpu fragmentation.


Para evitar desbalanceo de carga por parte del scheduler, interprocess fairness es un buen criterio (si se va a quitar quantum a un job, que se le haga a todos los procesos de ese job, en round robin y no solo a uno).

En la sincronizacion, si es un barrier, lo mas importante es que sea balanceado, que este gang scheduled no sera de gran ayuda. Pero si es comunicacion punto a punto, gang scheduler si que ayudara.

Midiendo el ratio de media de mensajes cuando estan gang scheduled a cuando no lo están pueden sacar un "gangedness". Si una aplicación envia muchos mensajes estando gang scheduled, se pasa a no gang scheduled y se ve reducida la cantidad considerablemente, a parte de por casualidad por entrar en una seccion sin comm, es un indicador de que necesita estar gang scheduled. (si esto se repite varias veces, es aun más determinante de que lo es)


~~Beneficios de gang scheduling 1,3,9]
fine grain application beneficts 9]~~

Estudios que indican que las aplicaciones cientificas pueden consistir de basante IO por leer datos y escribir resultados ~~4,5]~~

online monitoring para gangedness ~~17~~, 10] 
10, [[Coscheduling_based_on]]


"We envision a scheduling strategy exible enough to accommodate all jobs. I/O-bound jobs can have either coordinated I/O or uncoordinated I/O. Compute bound jobs may either be perturbation-friendly or perturbation-sensitive. Scheduling would be done in two sets of rounds. Uncoordinated I/O-bound jobs and perturbation-friendly compute-bound jobs are scheduled in rounds with loose coordination. Coordinated I/O-bound jobs and perturbation-sensitive compute-bound jobs can be scheduled in rounds with strict coordination."