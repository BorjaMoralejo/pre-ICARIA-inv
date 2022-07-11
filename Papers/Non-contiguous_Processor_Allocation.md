#coscheduling 
#key 

[[Non-contiguous_Processor_Allocation.pdf]]

Dice de repartir los trabajos no contiguamente, parecido a job stripping [[The_case_for_colocation_of_high_performa]]. 


Primero mira si la contención por parte del network va a ser un problema, y ven que no lo va a ser. Hacen pruebas pero el mayor slowdown es de 2% y lo que podría a considerarse ralentizado es un artefacto del sistema operativo. Incluso incrementando el tamaño de los mensajes no consiguer saturarlo por contención.

Si de verdad no causa retraso, esto acaba con la internal fragmentation y external fragmentation, y solo habría que buscar jobs con el número de procesos necesario para rellenarlo.

Tienen que tener paso de mensajes de wormhole.