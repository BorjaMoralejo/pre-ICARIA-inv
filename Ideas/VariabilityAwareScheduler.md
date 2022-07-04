#idea 
[[Ideas]]

Algo "sencillo" comparado con el anterior, conseguir variabilidad de las CPUs de los nodos. Y si estas loco, de los cores, esto no lo he visto que se haya hecho y creo que es demasiado a detalle... Con esa variabilidad que se obtiene cuanto tiempo y uso de energía (medido con RAPL) se pueden conseguir CPUs "lentas" y "rapidas" a las que se le pueden meter tareas cpu intensive o memory intesive (esto no he visto en ningun articulo, que usen la variabilidad de fabrica de la cpu si, pero no para coschedulear de esta forma).


Se ha comprobado en [[Power_Efficient_Job_Scheduling_by_Predicting]] que para realizar la misma tarea, el consumo y tiempo de las ejecuciones cambian según el chip que se utiliza por las variaciones que tienen de fábrica. 

A las CPUs con menor velocidad se le pueden asignar las tareas que sean memory intensive o high cache missrate, y a las tareas que son CPU intesive, las CPUs más rápidas. 

En un cluster hay muchos cores (10k o más) así que habrán muchas variaciones y esto puede ayudar a reducir el consumo energético bastante.

Todo esto teniendo en cuenta (el coscheduling está ya incluido de por sí por la diferenciación de las CPUs):
* Consolidation, por el mero hecho de que se quieren utilizar el mayor número de recursos posibles (y de forma eficiente, o eso se busca) +
* + Backfilling, aprovechar el "hueco" sobrante del sistema tras asignar la tarea principal y rellenear los huecos con tareas que no interfieran. [[backfilling_paper]]
* Esto seria opcional y más como prueba, he leido que hay modulador de voltage de la cpu y se decrementa en cores idle [[PowerNap_Eliminating_Server_Idle_Power]], pues seria usar algo asi pero en las memory intensive y mirar si da resultados. Aunque creo que esto queda mejor como otra idea de investigación, esta ya tiene muchas cosas.

Luego la machine learning tendría su sitio como clasificador para predecir si van a interferir o no (ya sea para coschedulear, o para backfillear, que es lo mismo, backfilling es una forma de coscheduling) 

Igual me estoy flipando demasiado xd