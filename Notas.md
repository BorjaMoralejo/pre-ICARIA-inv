Esta estructurado de la siguiente forma:
Doing: directorio que contiene ficheros con descripción o enlaces a otros ficheros sobre articulos que se han leido
[[Doing]] (este es el fichero que engloba todos)

Ideas: no hace falta que lo explique, no?
[[Ideas]] (otro que engloba + mini descripcion)

Papers: Aquí estan los archivos que se referencian desde doing y tienen el enlace a su propio pdf (mismo nombre que fichero)

PDF: pues eso, los pdfs


Los papers estan relacionados con etiquetas, como # consolidation y # machine_learning. Algunas más utiles que otras, pero soy nuevo usando obisidian

A lo largo del trabajo ire apuntando en este doc cosas que me llamen la atención y si es necesario lo enlazaré a otro archivo


















# Pasado de TODO hasta aquí

---------------------


buscar info sobre datos de consumo electrico de los centros de datos y supercomputadores
	Related: GCA4489, DYNAMIC TASK SCHEDULING USING PARALLEL GENETIC ALGORITHMS FOR HETEROGENEOUS DISTRIBUTED COMPUTING 
	[[DYNAMIC_TASK_SCHEDULING_USING_PARALLEL]]
ever-increasing computational requirements [3]


--------------
razones que causan malas interacciones entre hilos
	Load imbalance, asignacion de recursos pobre:
	including data contention, work partitioning overheads, large serial portions, and contention for shared architectural resources
	Multiple resources, including the cache, execution units, TLBs, branch predictors
	bigdata_and_hpc_FINAL_20Nov18 da las causas en pag 8


--------------- 
obtener porcentaje de consumo electrico de los supercomputadores, que parte esta relacionada con la refrigeracion y que parte a power supply.
	No he buscado aun esto

---------

buscar diferentes aplicaciones de los supercomputadores
	Meteorologia, aplicaciones cientificas que simulan comportamientos de materiales, biomedicina, nanotecnología, polimeros y soft matter, componentes químicos...
	El tiempo de investigación de estos estudios es acelerado por los centros HPC,

-----------
mirar gang scheduling // DONE, un poco triste mirarlo desde wikipedia, de su creador, [[Ousterhout]] y [[Contributions_to_Gang_Scheduling]] pero xd (tengo uno abierto en tabs, al final no se si acabara aqui)

----------

symbiotic job scheduling, imposible, esta en un libro y de todos modos parece que es consolidation pero con mas detalle en el analisis de las interacciones

------------
poner sources a lo de abajo para cuando se hagan referencias en el informe:



Diversas tecnicas para reducir el consumo
	Power nap and Cpu Throttling, nah, pero falta poner el source que lo tendre por algun lado (y mas que CPU throtling, mejor variant aware scheduling)
	Consolidar los procesos (relacionado con co-scheduling, no va consolidation solo pero si coscheduling solo)
		Cualquiera que hable de # consolidation  (todo junto en el buscador, son unos cuantos)
	Co-scheduling
		Teniendo en cuenta las caracteristicas como cache miss y memory bus...: 
			Scheduling Algorithms for Effective Thread Pairing on Hybrid Multiprocessors, Symbiotic jobscheduling
			_
		Teniendo en cuenta los datos: 
			[[Co-Scheduling_of_Computation_and_Data_on_Computer]]
		 _
	job stripping, The Case For Colocation of HPC Workloads
	Variant aware scheduling [[Power_Efficient_Job_Scheduling_by_Predicting]] 
	Hacer que se lancen menos jobs inutiles que se acaban cancelando o acabando por falta de recursos [[Deep_Analysis_of_Job_State_Statistics]]
Luego hay otros de machine-learning pero se basan en estos anteriores y usan clasificadores para, clasificarlos, y luego usa una politica mas o menos "innovadora" y ya tienen articulo.