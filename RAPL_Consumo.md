
- [ ] Integrar RAPL en una aplicación propia a partir de la interfaz. Lo que busco con esto es que no muestre datos que no interesan (y que no muestre por pantalla los datos tampoco)
- [ ] Hacer que recolecte datos de forma automática para generar medias y eso. Primero será un consumo general, las instrucciones que hace por ciclo y algún que otro dato que me de la aplicación.
- [ ] Obtener perfil "Idle" del portatil, supongo que se usara el core 0 más que ningún otro. Siempre tengo la opción de pasar a otra distribución linux que no consuma tanto (ya que el escritorio interactivo sigue siendo un proceso a parte y algo consume) pero voy a intentar obtenerlo de todos modos, creo que va a ser más sencillo. No puedo virtualizar debido a que el consumo idle ahora se le estaría sumando el costo de la virtualización. Tomaré el consumo de media como perfil idle.
- [ ] Obtener datos de ejecución de otros cores lanzando la practica de SCP (o mejor un benchmark que se sepan los datos) en un unico core. Para ello los tendré que lanzar con afinidad y tener en cuenta el perfil idle. De nuevo, el perfil idle = consumo de media, aunque con el core 0 puede tener algun problema por los cambios de contexto y prioridad de los procesos.
- [ ] Analizar los datos y ver si hay alguna diferencia mínima (no he mirado si hay variación a nivel de core, se que a nivel de socket sí que hay).
	* Si no hay diferencia, lo siguiente solo se hace con un core, si no, se hace con todos: se perfilará y analizará para sacar la eficiencia IPC/W de los cores.
	* Si hay diferencia, hacer que el programa lo obtenga y guardarlo de forma estructurada para que se pueda utilizar con el scheduler que se desarrolle en algun momento futuro.


