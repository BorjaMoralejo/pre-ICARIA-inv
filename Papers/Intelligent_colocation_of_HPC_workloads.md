#machine_learning 
#coscheduling 

#consolidation  

#measured 
#parsec 
#slurm

#key 


[[Intelligent_colocation_of_HPC_workloads.pdf]]


Este artículo es lo que tenia en mente hacer, pero parece que ya se ha hecho. Lo han implementado con un plugin de Slurm.

Utiliza machine learning y contadores del hardware.

5] la factura de la luz puede llegar a ser, durante el ciclo de vida del HPC, el mismo que el coste de construirlo.

Habla del RAPL y lo referencia en ~~9]~~ Manual https://www.intel.es/content/www/es/es/architecture-and-technology/64-ia-32-architectures-software-developer-vol-1-manual.html


Más info sobre workload colocation 2,3,13,14,15,1] (pero tiene toda la pinta de ser coscheduling y consolidation)

2, [[Increasing_Utilization_in_Modern_Warehouse]]
3, Relacionado con el anterior, [[Precise_Online_QoS_Management]]
~~13~~, Energy-aware thread co-location, pero para sistemas con cores heterogeneos. El homogeneo no consigue nada beneficioso. Eso es porque se utilizan los cores "pequeños" y "grandes" por separado y se asignan diferentes tareas a ellos.
~~14, colocation en data centers metiendo profiler desde compilador~~
15, [[A_Practical_Method_for_Estimating_Performance]]
1, [[Intelligent_Colocation_of_Workloads_2.pdf]] (de los mismos autores y con un titulo casi exacto).




Menciona que el colocation puede ser beneficioso o puede que no, según el uso de recursos, así que tiene toda la pinta de es consolidation y coscheduling.

Usa PARSEC, Splash y otros.



Otros coscheduling 20,21,22] que usan los contadores hardware.
20 [[Contention-Aware_Scheduling]]
21 [[Resource-conscious_Scheduling_for_Energy]]
22 [[A_Machine_Learning_Approach_to_Predicting]]

Requiere de una ejecución previa de cada aplicación... Y tiene que ser uno a uno para coger los datos.

Microbenchmarking 2], Bubble up, mencionado previamente

La tabla 1 tiene muchos atributos que se sacan de los contadores.

Se implementa como plugin de Slurm.

Implementado en slurm 37] [[Adaptive_Resource_and_Job_Management]]
Power aware Slurm 38,39]
40] otro power aware pero para los sistemas que les sobran hardware. No demasiado util para nuestro caso
38, [[A_Unified_Platform_for_Exploring_Power]]
39, lo mismo que 37 y 38, power aware para power capped.

~~42,43,12,44~~ usan RAPL para mejorar la eficiencia y system throughput pero de nuevo, bajo power capped y se centran más en eso



Más machine learning 15] mirando colocation, esta realmente bien.
49] consolidation max

