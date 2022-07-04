#idea 
Estos son los conceptos sueltos que he ido recogiendo:
* coscheduling (y consolidation)
	* Teniendo en cuenta: missrate, bus use, cpu use... (consolidation)
	* job-stripping (otra forma de consolidation)
	* backfilling (otra forma de consolidation, meter mas en menos espacio)
* power aware (los que he visto son para limitar el consumo... no se si hyperion o atlas necesitan eso...)
* variability aware
* runtime y predicciones de fallo (la ultima es un poco extraña a mi parecer pero bueno)


------------
No he visto que haya ningun clasificador de tipos de tareas y tamaño combinado con job stripping. Esto deberia clasificarlo segun la cantidad de recursos que utilice.
[[ML+Size]]

-------------------------

Otra cosa, aunque ya se ha utilizado, es para predecir si un runtime estara mal puesto (aunque no es dificil ya que parece que se suelen sobreestimar los tiempos y recursos, y un predictor que diga que si va a tener más probabilidad de acertar).
[[RuntimePred]]


------

Hacer job striping y tener en cuenta el uso de recursos. 
[[IntelligentJobStripping]]

-----

Perfilado de aplicaciones en runtime (puede llegar a ser demasiado costoso, pero la idea es pillar el perfil de recursos utilizados para coschedulear). 
[[ProfilingScheduling]]

-----

Esto son cosas extras que se podrían añadir para mejor clasificación por parte del usuario

Se pueden pedir otros parametros a los usuarios, como numero de iteraciones, tiempo estimado de iteracion y desviación de las iteraciones. Si alguno de estos valores es desconocido o demasiado variable, se podría especificar con algún valor para que se tenga en cuenta o no.


---------------

Al crear el nuevo supercomputador Hyperion, ¿de dónde saca la energía? ¿De la misma planta que Atlas? Si es así, ¿es posible que llegue a superar el límite energético impuesto por el sumistrador de energía? Si no hay ningún problema pues nada, pero si existe la posibilidad, estaría bien mirar un coordinador de power aware schedulers para que no se pasen de consumir energía y que se queden los dos sin energía o uno de ellos se acabe apagando.

[[Adaptive_Resource_and_Job_Management]]

---------
Tener en cuenta el job stripping the [[The_case_for_colocation_of_high_performa]] en algunos de los puntos anteriores e investigar cuando viene bien hacerlo y cuando no.

------------
Combinar power aware con consolidation, es decir, que no solo limite la energia por nodo, si no que se tenga en cuenta el coscheduling de las tareas. (en si es coscheduling pero con el power aware...)

-------

Otra idea random, intentar cambiar los algoritmos clasificadores heuristicos de algunos articulos por uno de machine learning.

------

Combinar con lo que cambia la tension de la CPU para los que tengan mucho acceso de memoria para reducir el consumo. 

----

De todas las ideas esta es la que más me llama.

Algo "sencillo" comparado con el anterior, conseguir variabilidad de las CPUs de los nodos y coschedulear inteligentemente. 
[[VariabilityAwareScheduler]]

