[[Ideas]]

#idea

Hacer job striping y tener en cuenta el uso de recursos. (+ backfilling)

Si hay dos tareas ejecutandose, que una sea la principal y otra la secundaria y que tenga prioridad la principal. (esto que en su momento lo escribi sin leer demasiado, no sabia que era backfilling)

Si llega un punto en el que los dos estan fallando mucho de cache, se cambia el secundario por uno que se sepa que falla mucho de tlb y el que se retira se quedaria marcado como que falla de cache(+ otras propiedades anteriores, al ser la mayoria iterativos). Sería migrar tareas a otros cores con menos uso de cache.

[[Improving_the_Performance_of_Batch_Schedulers]]
[[backfilling_paper]]
[[The_case_for_colocation_of_high_performa]]

cualquiera de consolidation + coscheduling que se fije en los recursos, pero entre todos los que hay estos me llamaron la atención (deberia de haber uno que usa IA para pillar los recursos que mas causan los retardos)

[[An_approach_to_resource-aware_coscheduling_for_CMP]] 

[[Intelligent_colocation_of_HPC_workloads]]

[[Reducing_the_energy_cost_of_computing_th]]

[[A_Practical_Method_for_Estimating_Performance]]