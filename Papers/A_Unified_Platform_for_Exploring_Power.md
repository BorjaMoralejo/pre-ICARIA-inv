#slurm 
#key 

Creo que es muy parecido a lo que buscamos hacer

[[A_Unified_Platform_for_Exploring_Power.pdf]]

Al igual que [[Adaptive_Resource_and_Job_Management]], se encarga de no superar un powercap. Pero en este caso lo combinan con otro scheduler que busca colocar de forma eficiente las tareas.

RMAP, power aware backfilling pero necesita: jobs are moldeable y que exite un modelo para estimar la performance de la aplicacion.

El capitulo V habla de Slurm


Optimizaciones del thoughtput buscan reducir el average turnaround time 4,11] y eso se busca en el paper tambien.

Tiene implementaciones de los schedulers como plugins de SLURM, voy a leerlo solo por eso.

SLURM provides the Select plugin with a job description via a job record struct pointer, and the available resources via a bitmask pointer
