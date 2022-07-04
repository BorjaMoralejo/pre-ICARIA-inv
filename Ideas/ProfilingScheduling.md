[[Ideas]]

#idea 

Perfilado de aplicaciones en runtime (puede llegar a ser demasiado costoso, pero la idea es pillar el perfil de recursos utilizados para coschedulear). 

Aquí se podría usar machine learning (y otras cosas). La cosa sería detectar los bucles de las iteraciones, como vimos en ikerlan con el que analizaba las señales electromagneticas, pero a nivel de perfilado de: high cache miss, high tlb miss, io, comms... La idea es sacar patrones. Y si se saca un patrón, se podría combinar con otro que sea compatible y hacer coscheduling.

Siempre se puede usar la parte de perfilado sin tanto detalle para otros coschedulers de todos modos. Lo principal de esta idea seria sacar un perfil de la aplicación sin información previa y que se pueda clasificar para coschedulear. 


[[Power_Signatures_of_High_Performance_Com]]

