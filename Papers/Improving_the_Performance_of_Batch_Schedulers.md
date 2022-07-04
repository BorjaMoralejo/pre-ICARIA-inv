#machine_learning 

#slowdown
#online

[[Improving_the_Performance_of_Batch_Schedulers.pdf]]

Es un clasificador que los agrupa en tareas grandes o pequeñas, y según la clasificación, luego un sistema de scheduleo ya existente las mete. Estos existentes priorizan las tareas pequeñas para incrementar el flujo de tareas y acabar con latencias ~~**13]**~~, pero seguramente tengan el problema de inanición. Se suele utilizar **SPF 6]**[[Characterization_of_Backfilling_Strategies_for_Parallel_Job_Scheduling.pdf]], Shortest Processing time First



--------

Backfilling: dejar adelantar a un task si no ralentiza al primero y si hay hueco, **7]** [[backfilling_paper.pdf]]
Highly overstimated runtimes by users **8]** [[Backfilling_Using_System_Generated_Predictions.pdf]].

Dicen que son capaces de demostrar que el conocimiento minimo del tamaño de la tarea es suficiente para compararlo con schedulers clarividentes, que saben de muchos más datos a priori.

Dynamic scheduling policies using machine learning **17]**, que apenas se aplican por el lio que tienen que hacer los admins del sistema.


En caso de necesitarlo, metricas para el costo de los HPC **20]**

Las features que se utilizan para clasificarlo me parecen un poco extrañas, las temporales más que cualquier otra:

| Tipo | Feature | Descripción |
|---|---|---|
|Job feature | pi | user supplied runtime estimate |
||qi|user supplied number of resources|

Temporal features como hora, dia de la semana, dia del mes, mes, semana, cuatrimestre...

Datos de las ejecuciones anteriores, las clasificaciones que fueron (las predicted y las actuales)

Aggregation features, datos previos e historicos.


Si me va a tocar mirar formas de usar machine learning, random forest **23]**





Reducir el tiempo de espera puede estar bien, pero no es suficiente. Hacer todo ese trabajo para conseguir que se ejecuten en el mismo tiempo y no tiene en cuenta el batch scheduling o gang scheduling, algo que debería de tener en cuenta ya que se suelen lanzar varios trabajos relacionados.
