#parsec 
#measured 

#offline

#consolidation 



[[Mapping_Dynamic_Workloads_of_Colocated_Multithreaded.pdf]]

Dey et al. 2011 tambien hacen multithreaded

"Online" thread mapping algorithm que detecta y evita contención. Lo ponen como online pero necesita su parte offline que es la que calcula los scores de sensitividad. No sirve demasiado entonces, pero la idea de mappear los threads para reducir la contención está ahí.


Tiene una tabla con otros sistemas parecidos, 

Pusukuri et al 2013
Bhadauria et al 2010 
Tang et al 2011


No lo termino de leer, pero esto se puede aplicar a aplicaciones que se repitan mucho en el sistema. Pero solo eso, si añades una nueva, tienes que medir el rendimiento de dos formas antes de poder schedulearlo bien.