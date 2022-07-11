#coscheduling 
#slurm 
#machine_learning 
#parsec 
#measured 
#power
#research Tiene un huevo de referencias a otros trabajos relacionados con la varaición de los sockets

[[Power_Efficient_Job_Scheduling_by_Predicting.pdf]]

Utiliza las variaciones de los chips para conseguir mejor rendimiento.
PMC
Performance Monitoring Counters

Usa un benchmark para conseguir el consumo de recursos de los cores utilizados y a partir de eso continua

Predicen con bastante precisión la potencia que va usar un socket para una aplicación. Figura 3, 3 CPUs "diferentes" (la misma pero con las variaciones de fabrica) pero 3 predicciones correctas

Usan los ratios consguidos del benchmark de cholesky.
Requiere una ejecución previa de las aplicaciones en un socket de referencia.


Para las aplicaciones multithreaded tiene que sacar el profile a cada uno de los hilos.

![[Pasted image 20220701120431.png]]


También usan NAS benchmark, que lo he leido en otros papers, se menciona frecuentemente.

Comentan que no pueden usar RAPL porque requiere de permisos de root.

Usan perf como profiler


6,~~7~~] Analisis de las pequeñas variaciones en la arquitectura afectan a la potencia
6 Systematic Energy Characte

13, 54] usan variability en scheduling
13 runtime guided
54] [[Scheduling_for_HPC_Systems]]


~~4,~~13,~~16,22,27,~~53,54]



53 [[Variation-Aware_Application_Scheduling]]
Ojo, 39], manufacturing variability is going to increase.
