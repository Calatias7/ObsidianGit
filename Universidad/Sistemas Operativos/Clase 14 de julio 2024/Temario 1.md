### MÓDULO I – Panorama General de los Sistemas Operativos

#### Semana 1: Hardware y Software de la Computadora
- **Hardware:**
  - **CPU (Unidad Central de Procesamiento):** El cerebro de la computadora que ejecuta instrucciones y procesa datos.
  - **RAM (Memoria de Acceso Aleatorio):** Almacena datos temporales y es volátil.
  - **Almacenamiento (Discos duros, SSDs):** Almacena datos de forma permanente.
  - **Periféricos (Teclado, ratón, impresora):** Dispositivos externos que interactúan con la computadora.

- **Software:**
  - **Sistema Operativo (OS):** Administra hardware y software, proporciona servicios a otros programas. Ejemplos: Windows, Linux, macOS.
  - **Software de Aplicación:** Programas diseñados para realizar tareas específicas. Ejemplos: Microsoft Office, navegadores web.
  - **Software de Utilidad:** Realiza tareas de mantenimiento y gestión del sistema. Ejemplos: Antivirus, herramientas de disco.


#### Semana 2: Perspectiva de los Sistemas Operativos
- **Funciones principales:**
  - **Gestión de Procesos:** Controla la ejecución de programas.
  - **Gestión de Memoria:** Administra la memoria del sistema.
  - **Gestión de Archivos:** Controla la creación, eliminación y acceso a archivos.
  - **Gestión de Dispositivos:** Administra dispositivos de hardware y sus controladores.

- **Tipos de Sistemas Operativos:**
  - **Monousuario:** Un solo usuario utiliza el sistema a la vez.
  - **Multiusuario:** Permite que varios usuarios usen el sistema simultáneamente.
  - **Tiempo Real:** Responde a eventos en tiempo real.
  - **Distribuidos:** Controla múltiples computadoras como un solo sistema.


#### Semana 3: Gestión de Procesos
- **Definición de Proceso:** Un programa en ejecución, incluyendo el código del programa, sus datos y su estado.
- **Estados de un Proceso:**
  - **Nuevo:** El proceso está siendo creado.
  - **En Ejecución:** El proceso está siendo ejecutado por la CPU.
  - **Esperando:** El proceso está esperando algún evento.
  - **Listo:** El proceso está esperando ser asignado a la CPU.
  - **Terminado:** El proceso ha finalizado su ejecución.
- **Control de Procesos (PCB):** Contiene información sobre el proceso, como el estado del proceso, contador de programa, registros, información de memoria, etc.


#### Semana 4: Planificación de Procesos
- **Concepto:** Determinar qué procesos deben ser ejecutados por la CPU y en qué orden.
- **Algoritmos de Planificación:**
  - **FIFO (First In, First Out):** Los procesos se ejecutan en el orden en que llegaron.
  - **SJF (Shortest Job First):** El proceso con el menor tiempo de ejecución se ejecuta primero.
  - **Round Robin:** Cada proceso recibe un tiempo de CPU igual en ciclos rotativos.
  - **Prioridad:** Los procesos se ejecutan según su prioridad asignada.


#### Semana 5: Algoritmos de Planificación
- **Análisis de Rendimiento:**
  - **Tiempo de Espera:** Tiempo que un proceso espera en la cola de listos.
  - **Tiempo de Retorno:** Tiempo total que tarda un proceso desde su llegada hasta su finalización.
  - **Rendimiento:** Número de procesos que se completan en una unidad de tiempo.
  - **Utilización de CPU:** Porcentaje de tiempo que la CPU está en uso.


### MÓDULO II – Concurrencia e Interbloqueos

#### Lección 6: Concurrencia
- **Concepto:** La ejecución de múltiples procesos o hilos simultáneamente.
- **Mecanismos de Concurrencia:**
  - **Hilos (Threads):** Unidades más pequeñas dentro de un proceso que pueden ejecutarse en paralelo.
  - **Procesos:** Programas independientes que se ejecutan simultáneamente.
- **Problemas Comunes:**
  - **Condiciones de Carrera:** Ocurren cuando varios procesos acceden y manipulan datos compartidos al mismo tiempo.
  - **Sección Crítica:** Parte del código donde se accede a recursos compartidos.


#### Lección 7: Interbloqueos
- **Definición:** Situación en la que dos o más procesos se bloquean mutuamente esperando recursos que los otros procesos poseen.
- **Condiciones para Interbloqueo:**
  - **Exclusión Mutua:** Los recursos no pueden ser compartidos.
  - **Retención y Espera:** Un proceso retiene recursos y espera otros adicionales.
  - **No Apropiación:** Los recursos no pueden ser forzadamente retirados de los procesos.
  - **Espera Circular:** Existe una cadena circular de dos o más procesos, cada uno esperando un recurso que posee el siguiente.
- **Métodos de Prevención y Recuperación:**
  - **Prevención:** Evitar al menos una de las condiciones necesarias para el interbloqueo.
  - **Recuperación:** Detectar el interbloqueo y tomar acciones para resolverlo, como matar procesos.


### MÓDULO III – Gestión de Memoria

#### Lección 8: Gestión de memoria en sistemas mono programados
- **Concepto:** La gestión de la memoria en sistemas que ejecutan un solo proceso a la vez.
- **Técnicas de Gestión de Memoria:**
  - **Particiones Fijas:** La memoria se divide en regiones de tamaño fijo.
  - **Particiones Dinámicas:** La memoria se asigna según el tamaño requerido por el proceso.


#### Lección 9: Gestión de memoria en sistemas multi programados
- **Diferencias con Mono Programación:** Permite la ejecución de múltiples procesos simultáneamente.
- **Técnicas de Gestión de Memoria:**
  - **Memoria Virtual:** Permite que los procesos utilicen más memoria de la que realmente está disponible en el sistema.
  - **Paginación:** La memoria se divide en bloques de tamaño fijo llamados páginas.
  - **Segmentación:** La memoria se divide en segmentos de tamaño variable según las necesidades del proceso.


#### Lección 10: Asignación de memoria contigua y no contigua
- **Asignación Contigua:**
  - **Definición:** La memoria se asigna en un bloque continuo.
  - **Ventajas:** Acceso rápido.
  - **Desventajas:** Fragmentación externa.

- **Asignación No Contigua:**
  - **Definición:** La memoria se asigna en bloques no continuos.
  - **Ventajas:** Mejor utilización de memoria, menos fragmentación.
  - **Desventajas:** Acceso más lento.


#### Lección 11: Memoria Virtual
- **Concepto:** Técnica que permite a los programas utilizar más memoria de la disponible físicamente mediante el uso de disco duro.
- **Técnicas de Implementación:**
  - **Paginación:** La memoria se divide en páginas y marcos de página.
  - **Segmentación:** La memoria se divide en segmentos que corresponden a diferentes partes del programa.
- **Ejemplos y Casos de Estudio:**
  - **Intercambio (Swapping):** Mueve procesos completos entre la memoria principal y el almacenamiento secundario.
  - **Administración de Tabla de Páginas:** Mapea las páginas virtuales a marcos de página físicos.
