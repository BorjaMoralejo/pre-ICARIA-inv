#machine_learning 
#online 
#consolidation 
#coscheduling 
#key 


[[A_Practical_Method_for_Estimating_Performance.pdf]]

Utiliza machine learning para estimar la degradación que van a tener.

Estudios demostrando la degradación en sistemas multicore 1-5] (3, 4 y 5 son modelos heuristicos)

No necesita aplicaciones en ejecuciones aisladas ni perturbar sus ejecuciones. Pero luego se contradicen al decir que usan los clock cycles de solo una instancia de una aplicación y de un conjunto de scheduling pero es porque lo entrenan offline.

Otro modelo propuesto 10]


Han utilizado CfsSubset para seleccionar los atributos 12] y muestra los atributos en una tabla, se podrían utilizar y ahorrar el análisis (Tabla III).


Memory bus contention is the key of degradation 5].

Usa un scheduler propio pero basado en Best-fit. Si hay degradación, se migran a otro nodo.

DI, Distributed Intensity, algoritmo para comprobar contención mirando la cache 3,4,17]


Acaba mencionando otros tres modos que se han utilizado para medir o estimar la contención: *analytical modeling* 5, 17] , *models based on heuristics* 3,4,5,17] y *trial-and-error methods* 7, 9].