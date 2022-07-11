#idea 

Vale, la idea es muy ambiciosa pero esto es lo que se me ha ocurrido después de leer los diferentes caminos que se pueden seguir para mejorar la eficiencia de diversas formas.

Se ha comprobado que dividir el trabajo en non contiguo no afecta demasiado a la performance siempre y cuando la red sea buena. [[Non-contiguous_Processor_Allocation]] y teniendo en cuenta lo de job-stripping, tambien viene bien [[The_case_for_colocation_of_high_performa]]

Esta siguiente matriz indica el reparto de los procesos en el conjunto de cores. Lo que buscan es conseguir un reparto que no despedicie recursos, como el cuadrado 4x4 de arriba, y repartirlo con cuadrados $2^{n}$. Pues sería hacer una división como está pero teniendo en cuenta el tiempo, porque está solo es espacial. Si la matriz se convierte en un array y se le añade el tiempo, tenemos la matriz de [[Ousterhout]]

![[Pasted image 20220707090728.png]] 

Como ya he mencionado, esta matriz se puede mejorar, eso se ha sacado de [[Non-contiguous_Processor_Allocation]] y es para la asignación de tareas para un tiempo en específico. El cubo 3d (matriz + dimensión de tiempo) se puede mejorar de la siguiente forma:

Teniendo en cuenta la variación de los diferentes procesadores como se tiene pensado en [[VariabilityAwareScheduler]] y se menciona en otros articulos de variability aware [[Variation-Aware_Application_Scheduling]]

Lo que ocurre es lo siguiente, dicen que la variación de los cores es hasta de un 20%. Como sacar provecho a esas variaciones tan grandes? Se me ha ocurrido subdividir la matriz aún más, puede que sea demasiado fragmentado pero junto a backfilling se saca provecho.



------------

Planteo el siguiente escenario muy naive y ultra simplificado:

El sistema tiene 2 cores, $C_0$ y $C_1$; Cada core tiene las siguientes variaciones:
$C_0$ es el doble de rápido que $C_1$
$f_0=2f_1$

La tarea 1 ($T_1$) tiene 2 hilos ($h_0, h_1$) y la tarea 2 ($T_2$) tiene 4 hilos y es "ligera" ($p_{0-3}$)(no voy a entrar si son CPU bound o memory bound para mantenerlo simple y que son totalmente balanceados)

-------------

Un scheduler normal haría lo siguiente:
A $C_0$ se le asigna $h_0,$ $p_0$ y $p_1$
A $C_1$ se le asigna $h_1,$ $p_2$ y $p_3$

La mátriz sería de esta forma:

Teniendo en cuenta que los intervalos $t$ tienen la misma duración.

| Core | $t_0$ | $t_1$ | $t_2$ | $t_3$ | 
|---|---|---|---|
|$C_0$| $h_0$| $p_0$| $p_1$
|$C_1$| $h_1$| $p_2$ |$p_3$


El caso es el siguiente: $C_0$ es el doble de rápido que $C_1$ y por lo tanto va a estar tiempo ocioso.
Si suponemos que en ese $t$ se llegan a ejecutar en su totalidad el trabajo de los procesos en $C_1$ (para evitar repetir ciclos y otras cosas que solo complicaría este modelo simplificado), llegamos a la conclusión de que $C_0$ está planificado $3t$ pero se llega a utilizar un 50% por ir al doble de velocidad. Por lo tanto está un $1.5t$ de trabajo (pero ocupado $3t$) y  $C_1$ está  $3t$ utilizado. $4.5t$ de uso en total en $3t$ o sobre $6t$ entre los dos.

Teniendo en cuenta que las tareas están balanceadas, ocurre un desbalanceo y hay un procesador que está un 50% ocioso, teniendo el sistema a un 75% de uso.

------------
Mientras que el scheduler que propongo haría lo siguiente:

Mediante una forma u otra, consigue los datos sobre la variabilidad de los cores y sabe que $f_0=2f_1$

La matriz no sería tan sencilla como la anterior, se dividiría de forma que se tenga en cuenta su minimo comun multiplo. Si ese número llega a ser demasiado pequeño, se multiplica por un número hasta que se consiga llegar a superar la $t$ que se busca.

De nuevo, para simplificar el modelo, voy a dividir entre 2 a $t$ (por el ratio de las frecuencias) y con ello se consigue el intervalo $q$.

La matriz quedaría de la siguiente forma:

| Core |[ $t_0$ | $t_0$ ]|[ $t_1$ | $t_1$]  | |
|---|---|---|---|---|
|  |[ $q_0$ | $q_1$] | [$q_2$ | $q_3$] | 
|$C_0$| $h_0$| $p_0$| $p_1$ | $p_2$ 
|$C_1$| $h_1$| $h_1$ | $p_3$ | $p_3$

En este modelo, $C_0$ completa 4 procesos en $2t$(al ir al doble de frecuencia)
y $C_1$ completa $2t$. Se ha usado el sistema al 100% e ignorando las sobrecargas que puedan surgir, se ha acelerado por 1.5 el tiempo de ejecución de la aplicación. 

Si solo el desenglose parece ser beneficioso, si se tiene en cuenta que separar las tareas entre diversos procesadores usando job-stripping o non-contiguous allocation mejora el rendimiento por repartir los recursso de forma homogenea entre el sistema, el incremento puede ser mayor (teniendo en cuenta que no se ejecuten en $t$ las tareas claro)

Y puede llegar a haber aún mejor rendimiento si se detectan segmentos memory bound o IO bound y se colocan en los cores más lentos, de forma que el tiempo perdido por el acceso a memoria o la espera de IO afecte en menor posible al rendimiento, pues el incremento del uso del sistema y de los recursos puede subir bastante.

Eso de repartir creo que se llama work stealing y sharing

Claro está que esta idea se tiene que ir implementando punto a punto.