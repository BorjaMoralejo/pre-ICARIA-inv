[[Ideas]]

#idea

No he visto que haya ningun clasificador de tipos de tareas y tamaño combinado con job stripping. Esto deberia clasificarlo segun la cantidad de recursos que utilice. 

Esto trata sobre [[Improving_the_Performance_of_Batch_Schedulers]], el primer apartado sería una forma de identificar si la tarea que se va a realizar es pequeña o grande, ahi es donde entra machine learning, y la otra parte seria hacer un scheduler que use backfilling (hay unos cuantos, uno de ellos se llama EASY backfilling y da buenos resultados, [[backfilling_paper]]) (que use [[Backfilling_Using_System_Generated_Predictions.pdf]] )

Pero que ese backfilling se haga junto con un job stripping.