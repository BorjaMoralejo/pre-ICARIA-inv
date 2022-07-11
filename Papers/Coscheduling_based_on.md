#coscheduling 
#key 

[[Coscheduling_based_on.pdf]]

El artículo busca conseguir working sets de los taks. Diciendolo de una forma un poco brusca, procesos de un job que tienen que coschedulearse si o si, pero que es posible que no sea tan estricto coschedulear con otro grupo de su propio job.

![[Pasted image 20220705071635.png]]

En esa imagen se puede ver que 1,2,3 forman un set, y 5,6,7 otro. Pues esos dos sets pueden (o no) coschedulearse por separado aunque sean del mismo job, y por lo tanto, poder meterse en "huecos" del coscheduling y aprovechar mejor el sistema.



Llegan a buscar estas agrupaciones según los Communications Objects que usan. Usan las estructuras de datos que usan en los programas, les añaden unos contadores de la frecuencia de uso y el tiempo de uso y con eso luego estiman los grupos. Las pruebas se han hecho con una aplicación sintetica, por lo que no es de mucho valor pero si que muestran que se pueden detectar working sets al mismo nivel que los introducidos manualmente por los usuarios.