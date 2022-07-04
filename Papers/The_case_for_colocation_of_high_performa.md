#consolidation 


[[The_case_for_colocation_of_high_performa.pdf]]


Hace job striping, separa lo que se podría hacer en un nodo en dos. Parece un poco useless pero si se combinan dos aplicaciones y se usa job stripping, se obtiene un incremento en throughput. Utiliza heuristica para determinar si es buena idea o no combinar dos tipos de tareas.

![[Pasted image 20220701082400.png]]

Dice que es bueno para aplicaciones que usan MPI y "real" HPC workloads.

21] perfil de aplicaciones de HPC

Tiene que samplear previamente. Para tomar las muestras de consumo de energia las toma de las PSU.

Unir multithread y uniprocess threads aumenta la eficiencia 7]
 Menciona el bubble up.