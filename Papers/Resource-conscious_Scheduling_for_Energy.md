#coscheduling 
#consolidation 

[[Resource-conscious_Scheduling_for_Energy.pdf]]


Migran tareas y las coschedulean y cambia la frecuencia del reloj de un chip entero. Lo integran en el kernel y en el KVM.

Trabajo anterior muestra que aligerar la contención de memoria incrementa la eficiencia 17]

Asume que las tareas no hacen IO y que se comunican entre ellas muy poco, es específico de tareas.


Este paper tambien llega a mencionar que la memory bandwidth es un recurso critico, aunque sea para esas benchmarks.

El CPU frecuency scaling no sale bien, al final consume más si se combinan todos los taks.

Otros coschedulers 11, 31]

No es facil comparar cuánta mejora obtienen con las politicas de scheduling y migracion por separado. Los datos positivos solo salen cuando se usan memory bound applications.

Detalla los elementos que ha utilizado para elegir el reparto, en el apartado de implementación.
Han tenido que modificar el kernel y desactivar el driver de control de tensión de la CPU para que lo puedan editar desde dentro del scheduler.

Usan taks de single thread...

