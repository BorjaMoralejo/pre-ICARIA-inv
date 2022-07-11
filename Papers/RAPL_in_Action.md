[[RAPL_in_Action.pdf]]


40] RAPL (pues no, es PAPI)
36] otro que usa RAPL para monitorizar
22] lo usa para perfilar
[[Adaptive_Power_Profiling.pdf]]

RAPL, Running Average Power Limit, se usa para monitorizar el consumo de potencia de ciertas partes de la CPU, la DRAM y la GPU integrada, Sandy Bridge y las siguientes arquitecturas vienen con esto.

El consumo energetico está en un registro donde 1 es (se accede con el msr driver):
Sandy Bridge uses energy units of 15.3 microjoules
Skylake uses units of 61 microjoules

*"For direct MSR access the MSR driver must be enabled and the read access permission must be set for the driver."* 

```c 
uint64_t msr_value;
/* Haswell: units of 61 microjoules */
/* MSR_PKG_ENERGY_STATUS is at address 0x611 */

double energy_units = pow (0.5, 14);
int fd = open ("/dev/cpu/0/msr", O_RDONLY);
if (fd < 0){
	perror ("open");
	return -1;
}
if (pread (fd, &msr_value, 8, 0x611) < 0){
	perror ("pread");
	return -1;
}

double energy = msr_value * energy_units;
printf ("%f\n", energy);

```

Se pueden leer también desde la interfaz sysfs, perf events o la libreria PAPI.
https://en.wikipedia.org/wiki/Perf_(Linux)#RAPL

Tambien con powercap

msr requiere de root.
perf no y esto indica como se programa 39] https://web.eece.maine.edu/~vweaver/projects/rapl/rapl-read.c

vmstat

RAPL está activado siempre, no hace falta configurarlo para ello.

RAPL no tiene timestamps, pero para ello: 14] 
[[Measuring_Energy_Consumption.pdf]]

y muestra que logra diferenciarse fases de ejecucion con 50Hz 35] [[Detailed_and_simultaneous_power.pdf]]



RAPL no mide cores individualmente, pero se pueden lanzar procesos unithreaded y medirlo (si el otro core esta durmiendo el consumo sera casi 0)
