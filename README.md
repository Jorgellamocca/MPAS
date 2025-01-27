# MPAS

Este tutorial está diseñado para ayudar a los principiantes a familiarizarse con el modelo MPAS-Atmosphere a través de una serie de ejercicios prácticos. Las secciones están organizadas de forma secuencial, y se recomienda seguir el orden establecido, ya que algunos ejercicios dependen de los resultados previos.

1. Requisitos Previos y Configuración del Entorno

Los ejercicios están diseñados para ejecutarse en el sistema Cheyenne, un clúster de alto rendimiento (HPC) que proporciona las bibliotecas necesarias para MPAS. Antes de comenzar, es fundamental configurar el entorno correctamente.

Pasos para la configuración

Purga de módulos:

module purge

Carga de módulos necesarios:

module load ncarenv/1.3 gnu/10.1.0 ncarcompilers/0.5.0 mpt/2.25
module load pnetcdf/1.12.2 netcdf-mpi/4.8.1 pio/2.5.5

Activación del entorno de Python:

module load conda
conda activate npl

Configuración de rutas adicionales:

export PYTHONPATH=/glade/p/mmm/wmr/mpas_tutorial/python_scripts
module load ncview
export PATH=/glade/p/mmm/wmr/mpas_tutorial/metis-5.1.0-gcc9.1.0/bin:${PATH}
module reload gnu

Para futuras sesiones, puedes copiar y pegar estos comandos para reconfigurar el entorno fácilmente.

2. Organización de los Archivos

Todos los ejercicios se ejecutarán en tu directorio de trabajo en Cheyenne:

mkdir /glade/scratch/$USER/mpas_tutorial
cd /glade/scratch/$USER/mpas_tutorial

3. Envío de Trabajos en Cheyenne

Dado que Cheyenne utiliza un sistema de colas para asignar recursos computacionales, es importante conocer los siguientes comandos básicos:

qcmd - Ejecuta un comando en un nodo de cómputo:

qcmd -A UMMM0002 <comando>

qsub - Envía un script de trabajo para ejecución en la cola.

qstat - Consulta el estado de los trabajos en la cola:

qstat -u $USER

qdel - Cancela un trabajo en ejecución o en espera.

