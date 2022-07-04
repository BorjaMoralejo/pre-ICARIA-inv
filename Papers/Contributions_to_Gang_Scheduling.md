#coscheduling 
#consolidation 

#no-use Esta mal.
[[Contributions_to_Gang_Scheduling.pdf]]


Es un gang scheduler que usa la matriz de [[Ousterhout]] pero que si ve que hay hueco, "duplica" alguna tarea. Lo que hace es que se ejecute más veces y que comparta el time slot con otro job.

Luego esta el compress gang scheduler, que disminuye el numero de procesadores del menos eficiente, algo complicado de implementar.

Esta tesis tiene mala pinta. Muestra mejoras abnormales que seguramente no sea por el coscheduling, si no por la contención, que no lo tiene en cuenta. Hay veces que le sale bien y otras que no. 

Puede que sean mejoras del gang scheduling pero solo si se sabe previamente que la compresión de los jobs no va a crear degradación del rendimiento por el comportamiento de los jobs. Al final es echar suertes. Por casualidad un workload consigue una mejora por el scheduler, que es lo que pasa con el workload 4, y se lo atribuye al scheduler, no al efecto de combinar ese tipo de aplicaciones. Además, la mejora del 288% es porque reduce el número de procesadores a la mitad, seguro que el reparto inicial es poco eficiente. 

