#coscheduling 

[[Flexible_coscheduling_mitigating.pdf]]

(se parece demasiado a [[Adaptive_parallel_job_scheduling_with_flexible_cos]], por no decir que son los mismos autores, sera alguna revision o algo idk)

Trata de conseguir crear un scheduler muy eficiente rellenando los huecos con tareas que permiten schedulearse por separado.

Tiene en cuenta el desbalanceo de las tareas que surgen por dos principales razones, por la aplicación y por la heterogeneidad del hardware. Por la aplicación ya sea por mala programación o por datos no iguales. La heterogeneidad de la aplicación lo tiene en cuenta por los diversos componentes que se van comprando a lo largo de la vida del cluster. 

Usa una clasificación muy parecida a [[Implications_of_IO_for_Gang_Scheduled_Workloads]] pero con menos detalle

Para estimar las comunicaciones han modificado la libreria de MPI para ello. Guardan el tiempo que usan en un espacio compartido y solo en comunicaciones bloqueantes.

La clasificacion de las tareas va cambiando segun la ejecucion y se categorizan por proceso, no por tarea. 


#idea 
Se pueden tomar los parametros que usan para clasificar y pasarlo por una red neuronal o algo para que lo clasifique "mejor", ya que la clasificacion es lineal y no basada en datos, si no por valores predeterminados.

Muestra que un scheduler especifico para ciertas tareas