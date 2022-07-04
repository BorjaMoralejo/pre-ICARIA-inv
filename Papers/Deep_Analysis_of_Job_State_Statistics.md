#slurm 

[[Deep_Analysis_of_Job_State_Statistics.pdf]]

Este paper busca las causas por las bajadas en eficiencia de los supercomputadores, en especifico Lomonosov-2, pero que seguramente se pueda aplicar al resto de HPC.

No solo mira causas de software, si no que también las causadas por usuarios: que se salten las cuotas y por ello se tenga que cancelar el job.

La eficiencia de los grandes HPC es baja 2] [[EfficiencyOfExascaleSupercompu.pdf]]

7] es otro trabajo parecido, viendo cuantos trabajos se cancelan. [[p14-zhang]]

Esto trata sobre los termination states de SLURM:

Una de las razones por las que llegaban al **timeout** es porque lo hacian queriendo. Es decir, que lanzaban las tareas teniendo eso en mente y cuando saliera el timeout se hacia un punto de control (porque ponian la ejecucion hasta el tiempo maximo permitido). Claro que habian otros que era porque no habian medido bien.

En **cancel** más de lo mismo y con otros casos como que lo cancelaban queriendo al terminar la tarea. Uno de los usuarios decia que cancelaba tareas para dar prioridad a otros jobs.

**Failed** ocurria por fallos con los nodos y problemas con MPI (he estado ahi con SCP) y otra causa es que los usuarios no usan la particion de pruebas.

