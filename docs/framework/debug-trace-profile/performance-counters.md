---
title: Contadores de rendimiento de .NET Framework
description: Obtenga información sobre los contadores de rendimiento en .NET. Hay contadores de rendimiento para las excepciones, la interoperabilidad, los compiladores JIT, la carga, la memoria, la red, la seguridad, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- performance, .NET Framework applications
- performance counters
- performance monitoring, counters
ms.assetid: 06a4ae8c-eeb2-4d5a-817e-b1b95c0653e1
ms.openlocfilehash: 3702e9d2e0a369f5391c16088202caf5d7ced7ea
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803708"
---
# <a name="performance-counters-in-the-net-framework"></a>Contadores de rendimiento en el .NET Framework

En este tema se proporciona una lista de los contadores de rendimiento que se pueden encontrar en el [monitor de rendimiento de Windows](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc749249%28v=ws.11%29).  

## <a name="exception-performance-counters"></a>Contadores de rendimiento de excepciones  
 La categoría de excepciones de .NET CLR de la consola de rendimiento incluye contadores que proporcionan información sobre las excepciones producidas por una aplicación. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**Número de excepciones iniciadas**|Muestra el número total de excepciones producidas desde que se inició la aplicación. Esto incluye las excepciones de .NET y las excepciones no administradas que se convierten en excepciones de. NET. Por ejemplo, un HRESULT devuelto desde código no administrado se convierte en una excepción en código administrado.<br /><br /> Este contador incluye excepciones controladas y no controladas. Las excepciones que se vuelven a producir se cuentan otra vez.|  
|**Número de excepciones iniciadas por segundo**|Muestra el número de excepciones producidas por segundo. Esto incluye las excepciones de .NET y las excepciones no administradas que se convierten en excepciones de. NET. Por ejemplo, un HRESULT devuelto desde código no administrado se convierte en una excepción en código administrado.<br /><br /> Este contador incluye excepciones controladas y no controladas. No es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras. Este contador es un indicador de posibles problemas de rendimiento si se produce un número grande de excepciones (>100).|  
|**Número de filtros por segundo**|Muestra el número de filtros de excepciones de .NET ejecutados por segundo. Un filtro de excepciones realiza una evaluación independientemente de si se controla una excepción.<br /><br /> Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Número de bloques Finally por segundo**|Muestra el número de bloques Finally ejecutados por segundo. Un bloque Finally se ejecuta independientemente de cómo se salió del bloque Try.  Solo se cuentan los bloques Finally ejecutados para una excepción; este contador no cuenta los bloques Finally de las rutas de acceso de código normales.<br /><br /> Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Profundidad por segundo de la instrucción Throw a la instrucción Catch**|Muestra el número de marcos de pila que se atraviesan por segundo, desde el marco que produjo la excepción hasta el marco que controló la excepción. Este contador se restablece a cero cuando se proporciona un controlador de excepciones, para que las excepciones anidadas muestren la profundidad de pila de controlador a controlador.<br /><br /> Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  

## <a name="interop-performance-counters"></a>Contadores de rendimiento interoperativos  
 La categoría de interoperabilidad de .NET CLR de la consola de rendimiento incluye contadores que proporcionan información sobre la interacción de una aplicación con componentes COM, servicios COM+ y bibliotecas de tipos externas. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**Número de CCW**|Muestra el número actual de contenedores CCW. Un CCW es un proxy para un objeto administrado al que se hace referencia desde un cliente COM no administrado. Este contador indica el número de objetos administrados a los que hace referencia el código COM no administrado.|  
|**Número de serialización**|Muestra el número total de veces que los argumentos y los valores devueltos se serializaron del código administrado al código no administrado y viceversa desde que se inició la aplicación. Este contador no se incrementa si los códigos auxiliares están entre líneas. (Los códigos auxiliares son responsables de serializar los argumentos y los valores devueltos). Los códigos auxiliares suelen estar entre líneas si la sobrecarga de serialización es pequeña.|  
|**Número de códigos auxiliares**|Muestra el número actual de códigos auxiliares creados por Common Language Runtime. Los códigos auxiliares son responsables de serializar los argumentos y los valores devueltos del código administrado al código no administrado y viceversa durante una llamada de interoperabilidad COM o una llamada Invoke de la plataforma.|  
|**Número de exportaciones TLB por segundo**|Reservado para uso futuro.|  
|**Número de importaciones TLB por segundo**|Reservado para uso futuro.|  

## <a name="jit-performance-counters"></a>contadores de rendimiento JIT  
 La categoría JIT de .NET CLR de la consola de rendimiento incluye contadores que proporcionan información sobre el código que se ha compilado mediante JIT. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**Número de bytes de IL con compilación JIT**|Muestra el número total de bytes de Lenguaje Intermedio de Microsoft (MSIL) compilados por el compilador Just-In-Time (JIT) desde que se inició la aplicación. Este contador es equivalente al contador **Número total de bytes de IL con compilación JIT**.|  
|**Número de métodos con compilación JIT**|Muestra el número total de métodos con compilación JIT desde que se inició la aplicación. Este contador no incluye los métodos compilados con PreJit.|  
|**% de tiempo de JIT**|Muestra el porcentaje de tiempo invertido en la compilación JIT desde la última fase de compilación JIT. Este contador se actualiza al final de cada fase de compilación JIT. Una fase de compilación JIT tiene lugar cuando se compilan un método y sus dependencias.|  
|**Bytes de IL con compilación JIT por segundo**|Muestra el número de bytes de MSIL con compilación JIT por segundo. Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Errores de JIT estándar**|Muestra el número máximo de métodos que el compilador JIT no pudo compilar desde que se inició la aplicación. Este error puede producirse si no es posible comprobar el MSIL o si hay un error interno en el compilador JIT.|  
|**Número total de bytes de IL con compilación JIT**|Muestra el número total de bytes de MSIL con compilación JIT desde que se inició la aplicación. Este contador es equivalente al contador **Número de bytes de IL con compilación JIT**.|  

## <a name="loading-performance-counters"></a>Cargar contadores de rendimiento  
 La categoría de carga de .NET CLR de la consola de rendimiento incluye contadores que proporcionan información sobre los ensamblados, las clases y los dominios de aplicación que se cargan. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**% de tiempo de carga**|Reservado para uso futuro.|  
|**Longitud de búsqueda de ensamblado**|Reservado para uso futuro.|  
|**Bytes del montón del cargador**|Muestra el tamaño actual, en bytes, de la memoria asignada por el cargador de clases en todos los dominios de aplicación. La memoria asignada es el espacio físico reservado en el archivo de paginación de disco.|  
|**Dominios de aplicación actuales**|Muestra el número actual de dominios de aplicación cargados en esta aplicación.|  
|**Ensamblados actuales**|Muestra el número actual de ensamblados cargados en todos los dominios de aplicación en la aplicación actualmente en ejecución. Si se carga el ensamblado con dominio neutro desde varios dominios de aplicación, este contador se incrementa solo una vez.|  
|**Clases cargadas actualmente**|Muestra el número actual de clases cargadas en todos los ensamblados.|  
|**Tasa de dominios de aplicación**|Muestra el número de dominios de aplicación cargados por segundo. Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Tasa de dominios de aplicación descargados**|Muestra el número de dominios de aplicación descargados por segundo. Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Tasa de ensamblados**|Muestra el número de ensamblados cargados por segundo en todos los dominios de aplicación. Si se carga el ensamblado con dominio neutro desde varios dominios de aplicación, este contador se incrementa solo una vez.<br /><br /> Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Tasa de clases cargadas**|Muestra el número de clases cargadas por segundo en todos los ensamblados. Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Tasa de errores de carga**|Muestra el número de clases que no se pudieron cargar por segundo. Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.<br /><br /> Pueden producirse errores de carga por muchas razones, como seguridad inadecuada o formato no válido. Para obtener más información, consulte la Ayuda de servicios de generación de perfiles.|  
|**Número total de errores de carga**|Muestra el número máximo de clases que no se pudieron cargar desde que se inició la aplicación.<br /><br /> Pueden producirse errores de carga por muchas razones, como seguridad inadecuada o formato no válido. Para obtener más información, consulte la Ayuda de servicios de generación de perfiles.|  
|**Número total de dominios de aplicación**|Muestra el número máximo de dominios de aplicación cargados desde que se inició la aplicación.|  
|**Número total de dominios de aplicación descargados**|Muestra el número total de dominios de aplicación descargados desde que se inició la aplicación. Si un dominio de aplicación se carga y se descarga varias veces, este contador se incrementa cada vez que se descarga el dominio de aplicación.|  
|**Número total de ensamblados**|Muestra el número total de ensamblados cargados desde que se inició la aplicación. Si se carga el ensamblado con dominio neutro desde varios dominios de aplicación, este contador se incrementa solo una vez.|  
|**Número total de clases cargadas**|Muestra el número acumulativo de clases cargadas en todos los ensamblados desde que se inició la aplicación.|  

## <a name="lock-and-thread-performance-counters"></a>Contadores de rendimiento de bloqueos y subprocesos  
 La categoría LocksAndThreads de .NET CLR de la consola de rendimiento incluye contadores que proporcionan información sobre los bloqueos y subprocesos administrados que usa una aplicación. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**Número de subprocesos lógicos actuales**|Muestra el número de objetos de subprocesos administrados actuales de la aplicación. Este contador mantiene el recuento de los subprocesos parados y en ejecución. Este contador no es un promedio a lo largo de un período de tiempo; solo muestra el último valor observado.|  
|**Número de subprocesos físicos actuales**|Muestra el número de subprocesos del sistema operativo nativo que creó Common Language Runtime y son propiedad de este, que actúan como subprocesos subyacentes para objetos de subprocesos administrados. El valor de este contador no incluye los subprocesos que usa el tiempo de ejecución en sus operaciones internas; es un subconjunto de subprocesos del proceso de sistema operativo.|  
|**Número de subprocesos reconocidos actuales**|Muestra el número de subprocesos reconocidos actualmente por el tiempo de ejecución. Estos subprocesos están asociados a un objeto de subproceso administrado correspondiente. El tiempo de ejecución no crea estos subprocesos, pero estos se ejecutaron al menos una vez en tiempo de ejecución.<br /><br /> Solo se realiza el seguimiento de los subprocesos únicos; los subprocesos con el mismo identificador de subproceso que se vuelven a entrar en tiempo de ejecución, o que se vuelven a crear después de que se cierre el subproceso, no se cuentan dos veces.|  
|**Número de subprocesos totales reconocidos**|Muestra el número total de subprocesos que reconoció el tiempo de ejecución desde que se inició la aplicación. Estos subprocesos están asociados a un objeto de subproceso administrado correspondiente. El tiempo de ejecución no crea estos subprocesos, pero estos se ejecutaron al menos una vez en tiempo de ejecución.<br /><br /> Solo se realiza el seguimiento de los subprocesos únicos; los subprocesos con el mismo identificador de subproceso que se vuelven a entrar en tiempo de ejecución, o que se vuelven a crear después de que se cierre el subproceso, no se cuentan dos veces.|  
|**Tasa de contención por segundo**|Muestra la velocidad a la que los subprocesos en tiempo de ejecución intentan adquirir un bloqueo administrado sin conseguirlo.|  
|**Longitud de cola actual**|Muestra el número total de subprocesos que están esperando para adquirir un bloqueo administrado en la aplicación. Este contador no es un promedio a lo largo de un período de tiempo; muestra el último valor observado.|  
|**Longitud de la cola por segundo**|Muestra el número de subprocesos por segundo que están esperando para adquirir un bloqueo en la aplicación. Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Máxima longitud de cola**|Muestra el número total de subprocesos que están esperando para adquirir un bloqueo administrado desde que se inició la aplicación.|  
|**Tasa de subprocesos reconocidos por segundo**|Muestra el número de subprocesos por segundo que reconoció el tiempo de ejecución. Estos subprocesos están asociados a un objeto de subproceso administrado correspondiente. El tiempo de ejecución no crea estos subprocesos, pero estos se ejecutaron al menos una vez en tiempo de ejecución.<br /><br /> Solo se realiza el seguimiento de los subprocesos únicos; los subprocesos con el mismo identificador de subproceso que se vuelven a entrar en tiempo de ejecución, o que se vuelven a crear después de que se cierre el subproceso, no se cuentan dos veces.<br /><br /> Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Número total de contenciones**|Muestra el número total de veces que los subprocesos en tiempo de ejecución intentaron adquirir un bloqueo administrado sin conseguirlo.|  

## <a name="memory-performance-counters"></a>Contadores de rendimiento de memoria  
 La categoría de memoria de .NET CLR de la consola de rendimiento incluye contadores que proporcionan información sobre el recolector de elementos no utilizados. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**Número de bytes en todos los montones**|Muestra la suma de los contadores del **Tamaño del montón de gen. 1**, **Tamaño del montón de gen. 2** y **Tamaño del montón del objeto grande**. Este contador indica la memoria actual asignada en bytes en los montones de recolección de elementos no utilizados.|  
|**Número de identificadores del GC**|Muestra el número actual de identificadores de elementos no utilizados en uso. Los identificadores de la recolección de elementos no utilizados son identificadores de recursos externos a Common Language Runtime y al entorno administrado.|  
|**Número de colecciones de gen. 0**|Muestra el número de veces que los objetos de generación 0 (es decir, los objetos asignados más recientemente) se recolectan como elementos no utilizados desde que se inició la aplicación.<br /><br /> La recolección de elementos no utilizados de generación 0 se produce cuando la memoria disponible en la generación 0 no es suficiente para satisfacer una solicitud de asignación. Este contador se incrementa al final de una recolección de elementos no utilizados de generación 0. Las recolecciones de elementos no utilizados de generación superior incluyen todas las recolecciones de generación inferior. Este contador se incrementa explícitamente cuando se produce una recolección de elementos no utilizados de generación superior (generación 1 o 2).<br /><br /> Este contador muestra el último valor observado. El valor del contador **_Global\_** no es preciso y debe omitirse.|  
|**Número de colecciones de gen. 1**|Muestra el número de veces que los objetos de generación 1 se recolectan como elementos no utilizados desde que se inició la aplicación.<br /><br /> El contador se incrementa al final de una recolección de elementos no utilizados de generación 1. Las recolecciones de elementos no utilizados de generación superior incluyen todas las recolecciones de generación inferior. Este contador se incrementa explícitamente cuando se produce una recolección de elementos no utilizados de generación superior (generación 2).<br /><br /> Este contador muestra el último valor observado. El valor del contador **_Global\_** no es preciso y debe omitirse.|  
|**Número de colecciones de gen. 2**|Muestra el número de veces que los objetos de generación 2 se recolectan como elementos no utilizados desde que se inició la aplicación. Este contador se incrementa al final de una recolección de elementos no utilizados de generación 2 (también llamada recolección completa de elementos no utilizados).<br /><br /> Este contador muestra el último valor observado. El valor del contador **_Global\_** no es preciso y debe omitirse.|  
|**Número de GC provocados**|Muestra el número máximo de veces que se realizó la recolección de elementos no utilizados debido a una llamada explícita a <xref:System.GC.Collect%2A?displayProperty=nameWithType>. Es conveniente dejar que el recolector de elementos no utilizados ajuste la frecuencia de las colecciones.|  
|**Número de objetos anclados**|Muestra el número de objetos anclados que se encontraron en la última recolección de elementos no utilizados. Un objeto anclado es un objeto que el recolector de elementos no utilizados no puede mover en la memoria. Este contador realiza un seguimiento de los objetos anclados únicamente en los montones que se recolectan como elementos no utilizados. Por ejemplo, una recolección de elementos no utilizados de generación 0 enumera los objetos anclados solo en el montón de generación 0.|  
|**Número de bloques de sincronización en uso**|Muestra el número actual de bloques de sincronización en uso. Los bloques de sincronización son estructuras de datos por objeto asignadas para almacenar información de sincronización. Contienen referencias débiles a objetos administrados y deben someterse al análisis del recolector de elementos no utilizados. Los bloques de sincronización no se limitan a almacenar información de sincronización; también pueden almacenar metadatos de interoperabilidad COM. Este contador indica problemas de rendimiento con un uso intensivo de primitivos de sincronización.|  
|**N.º total de bytes confirmados**|Muestra la cantidad de memoria virtual en bytes confirmada actualmente por el recolector de elementos no utilizados. La memoria asignada es la memoria física para la que se reservó espacio en el archivo de paginación de disco.|  
|**Número total de bytes reservados**|Muestra la cantidad de memoria virtual en bytes reservada actualmente por el recolector de elementos no utilizados. La memoria reservada es el espacio de memoria virtual reservado para la aplicación cuando no se usaron páginas de disco o de la memoria principal.|  
|**% De tiempo del GC**|Muestra el porcentaje de tiempo transcurrido que se dedicó a realizar una recolección de elementos no utilizados desde el último ciclo de recolección. Este contador suele indicar el trabajo realizado por el recolector de elementos no utilizados para recolectar y compactar la memoria para la aplicación. Este contador se actualiza solo al final de cada recolección de elementos no utilizados. Este contador no es un promedio; su valor refleja el último valor observado.|  
|**Bytes asignados por segundo**|Muestra el número de bytes por segundo que se asignan en el montón de recolección de elementos no utilizados. Este contador se actualiza al final de cada recolección de elementos no utilizados, no durante cada asignación. Este contador no es un promedio a lo largo del tiempo; muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Superviviente de finalización**|Muestra el número de objetos recolectados como elementos no utilizados que sobreviven a una recolección porque están a la espera de ser finalizados. Si estos objetos contienen referencias a otros objetos, esos objetos también sobrevivirán, pero este contador no los contará. El contador de **Memoria de finalización promocionada de gen. 0** representa toda la memoria que sobrevivió debido a la finalización.<br /><br /> Este contador no es acumulativo; se actualiza al final de cada recolección de elementos no utilizados con el recuento de los supervivientes solo en esa colección en particular. Este contador indica la sobrecarga adicional en la que podría incurrir la aplicación debido a la finalización.|  
|**Tamaño del montón de gen. 0**|Muestra el número máximo de bytes que se pueden asignar en la generación 0; no indica el número actual de bytes asignados en la generación 0.<br /><br /> Cuando las asignaciones desde la última colección superan este tamaño, se produce una recolección de elementos no utilizados de generación 0. El recolector de elementos no utilizados ajusta el tamaño de la generación 0 y este puede cambiar durante la ejecución de la aplicación. Al final de una colección de generación 0, el tamaño del montón de generación 0 es de 0 bytes. Este contador muestra el tamaño en bytes de las asignaciones que invoca la siguiente recolección de elementos no utilizados de generación 0.<br /><br /> Este contador se actualiza al final de una recolección de elementos no utilizados, no durante cada asignación.|  
|**Bytes por segundo promocionados de gen. 0**|Muestra los bytes por segundo que se promocionan de la generación 0 a la generación 1. La memoria se promueve cuando sobrevive a una recolección de elementos no utilizados. Este contador es un indicador de los objetos de una duración relativamente larga que se crean por segundo.<br /><br /> Este contador muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Tamaño del montón de gen. 1**|Muestra el número actual de bytes en la generación 1; este contador no muestra el tamaño máximo de generación 1. Los objetos no se asignan directamente en esta generación; se promocionan desde las recolecciones de elementos no utilizados de generación 0 anteriores. Este contador se actualiza al final de una recolección de elementos no utilizados, no durante cada asignación.|  
|**Bytes por segundo promocionados de gen. 1**|Muestra los bytes por segundo que se promocionan de la generación 1 a la generación 2. Los objetos que se promocionan únicamente porque están a la espera de ser finalizados no se incluyen en este contador.<br /><br /> La memoria se promueve cuando sobrevive a una recolección de elementos no utilizados. No se promueve nada desde la generación 2 porque es la generación más antigua. Este contador es un indicador de los objetos de una duración muy larga que se crean por segundo.<br /><br /> Este contador muestra la diferencia entre los valores observados en las dos últimas muestras divididos entre la duración del intervalo de obtención de muestras.|  
|**Tamaño del montón de gen. 2**|Muestra el número actual de bytes en la generación 2. Los objetos no se asignan directamente en esta generación; se promocionan desde la generación 1 durante las recolecciones de elementos no utilizados de generación 1 anteriores. Este contador se actualiza al final de una recolección de elementos no utilizados, no durante cada asignación.|  
|**Tamaño del montón del objeto grande**|Muestra el tamaño actual, en bytes, del montón de objetos grandes. Los objetos que superan aproximadamente 85.000 bytes se tratan como objetos grandes en el recolector de elementos no utilizados y se asignan directamente en un montón especial. No se promocionan a través de las generaciones. Este contador se actualiza al final de una recolección de elementos no utilizados, no durante cada asignación.|  
|**Identificador del proceso**|Muestra el identificador de proceso de la instancia de proceso CLR que se está supervisando.|  
|**Memoria de finalización promocionada de gen. 0**|Muestra los bytes de memoria que se promocionan de la generación 0 a la generación 1 solo porque están a la espera de ser finalizados. Este contador no es acumulativo; muestra el valor observado al final de la última recolección de elementos no utilizados.|  
|**Memoria promocionada de gen. 0**|Muestra los bytes de memoria que sobreviven la recolección de elementos no utilizados y que se promocionan de la generación 0 a la generación 1. Los objetos que se promocionan únicamente porque están a la espera de ser finalizados no se incluyen en este contador. Este contador no es acumulativo; muestra el valor observado al final de la última recolección de elementos no utilizados.|  
|**Memoria promocionada de gen. 1**|Muestra los bytes de memoria que sobreviven la recolección de elementos no utilizados y que se promocionan de la generación 1 a la generación 2. Los objetos que se promocionan únicamente porque están a la espera de ser finalizados no se incluyen en este contador. Este contador no es acumulativo; muestra el valor observado al final de la última recolección de elementos no utilizados. Este contador se restablece a 0 si la última recolección de elementos no utilizados era únicamente una colección de generación 0.|  

## <a name="networking-performance-counters"></a>Contadores de rendimiento de redes  

La categoría de redes de .NET CLR de la consola de rendimiento incluye contadores que proporcionan información sobre los datos que una aplicación envía y recibe a través de la red. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**Bytes recibidos**|El número total acumulativo de bytes recibidos por todos los objetos <xref:System.Net.Sockets.Socket> dentro del <xref:System.AppDomain> desde que se inició el proceso. Este número incluye datos y toda la información de protocolo no definida por TCP/IP.|  
|**Bytes enviados**|El número acumulativo de bytes enviados por todos los objetos <xref:System.Net.Sockets.Socket> dentro del <xref:System.AppDomain> desde que se inició el proceso. Este número incluye datos y toda la información de protocolo no definida por TCP/IP.|  
|**Conexiones establecidas**|El número total acumulativo de objetos <xref:System.Net.Sockets.Socket> para los sockets de secuencias que se conectaron alguna vez dentro del <xref:System.AppDomain> desde que se inició el proceso.|  
|**Datagramas recibidos**|El número total acumulativo de paquetes de datagramas recibidos por todos los objetos <xref:System.Net.Sockets.Socket> dentro del <xref:System.AppDomain> desde que se inició el proceso.|  
|**Datagramas enviados**|El número total acumulativo de paquetes de datagramas enviados por todos los objetos <xref:System.Net.Sockets.Socket> dentro del <xref:System.AppDomain> desde que se inició el proceso.|  
|**Duración promedio de HttpWebRequest**|El tiempo promedio para la finalización de todos los objetos <xref:System.Net.HttpWebRequest> que finalizaron en el último intervalo dentro del <xref:System.AppDomain> desde que se inició el proceso.|  
|**Promedio de tiempo en cola de HttpWebRequest**|El promedio de tiempo en cola de todos los objetos <xref:System.Net.HttpWebRequest> que abandonaron la cola en el último intervalo dentro del <xref:System.AppDomain> desde que se inició el proceso.|  
|**HttpWebRequests creadas por segundo**|El número de objetos <xref:System.Net.HttpWebRequest> creados por segundo dentro del <xref:System.AppDomain>.|  
|**HttpWebRequests en cola por segundo**|El número de objetos <xref:System.Net.HttpWebRequest> que se agregaron a la cola por segundo dentro del <xref:System.AppDomain>.|  
|**HttpWebRequests anuladas por segundo**|El número de objetos <xref:System.Net.HttpWebRequest> donde la aplicación llamó al método <xref:System.Net.HttpWebRequest.Abort%2A> por segundo dentro del <xref:System.AppDomain>.|  
|**HttpWebRequests con error por segundo**|El número de objetos <xref:System.Net.HttpWebRequest> que recibieron un código de estado de error del servidor por segundo dentro del <xref:System.AppDomain>.|  
  
 Se admiten varias clases de contadores de rendimiento de redes:  
  
- Contadores de eventos que miden el número de veces que se produjo un evento.  
  
- Contadores de datos que miden la cantidad de datos enviados o recibidos.  
  
- Contadores de duración que miden cuánto duran los diferentes procesos. El tiempo se mide en los objetos cada intervalo (normalmente en segundos) después de salir de estados diferentes.  
  
- Contadores por intervalos que miden el número de objetos que están realizando una transición determinada por intervalo (normalmente por segundo).  
  
Los contadores de rendimiento de red para eventos incluyen lo siguiente:  
  
- **Conexiones establecidas**  
  
- **Datagramas recibidos**  
  
- **Datagramas enviados**  
  
 Estos contadores de rendimiento proporcionan recuentos desde que se inició el proceso. Los recuentos de las conexiones de <xref:System.Net.Sockets.Socket> establecidas incluyen llamadas explícitas al método <xref:System.Net.Sockets.Socket> mediante una aplicación para una conexión de socket de secuencia establecida, así como llamadas internas realizadas por otras clases (<xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.WebClient> y <xref:System.Net.Sockets.TcpClient>, por ejemplo) a la clase <xref:System.Net.Sockets.Socket>.  
  
 Los recuentos de los **Datagramas recibidos** y los **Datagramas enviados** incluyen paquetes de datagramas enviados o recibidos mediante llamadas explícitas al método <xref:System.Net.Sockets.Socket> mediante una aplicación, así como llamadas internas realizadas por otras clases (<xref:System.Net.Sockets.UdpClient>, por ejemplo) a <xref:System.Net.Sockets.Socket>. clase. Los recuentos de los **Datagramas recibidos** y los **Datagramas enviados** también pueden usarse para proporcionar una medida aproximada de cuántos bytes se enviaron o recibieron mediante los datagramas, suponiendo un tamaño medio para un datagrama.  
  
 Los contadores de rendimiento de red para datos incluyen lo siguiente:  
  
- **Bytes recibidos**  
  
- **Bytes enviados**  
  
 Los anteriores contadores de rendimiento proporcionan recuentos de bytes desde que se inició el proceso.  
  
 Hay dos contadores de duración que miden cuánto tardaron los objetos <xref:System.Net.HttpWebRequest> en pasar a través de una parte o la totalidad de su ciclo de vida:  
  
- **Duración promedio de HttpWebRequest**  
  
- **Promedio de tiempo en cola de HttpWebRequest**  
  
 Para el contador de la **Duración promedio de HttpWebRequest**, la duración de la mayoría de los objetos <xref:System.Net.HttpWebRequest> siempre comienza con la hora en que se creó el objeto hasta la hora en que la aplicación cerró la secuencia de respuesta. Hay dos casos poco comunes:  
  
- Si la aplicación nunca llama al método <xref:System.Net.HttpWebRequest.GetResponse%2A> o <xref:System.Net.HttpWebRequest.BeginGetResponse%2A>, la duración del objeto <xref:System.Net.HttpWebRequest> se omite.  
  
- Si el objeto <xref:System.Net.HttpWebRequest> produce una <xref:System.Net.WebException> al llamar al método <xref:System.Net.HttpWebRequest.GetResponse%2A> o <xref:System.Net.HttpWebRequest.EndGetResponse%2A>, la duración finaliza cuando se produce la excepción. Técnicamente, la secuencia de respuesta subyacente también se cierra en ese momento (la secuencia de respuesta devuelta al usuario es realmente una secuencia de memoria que contiene una copia de la secuencia de respuesta).  
  
 Hay cuatro contadores que realizan el seguimiento de determinados problemas de los objetos <xref:System.Net.HttpWebRequest> por intervalo. Estos contadores de rendimiento pueden ayudar a los desarrolladores de aplicaciones, los administradores y el personal de soporte técnico a entender mejor lo que hacen los objetos <xref:System.Net.HttpWebRequest>. Los contadores incluyen lo siguiente:  
  
- **HttpWebRequests creadas por segundo**  
  
- **HttpWebRequests en cola por segundo**  
  
- **HttpWebRequests anuladas por segundo**  
  
- **HttpWebRequests con error por segundo**  
  
 Para el contador de **HttpWebRequests anuladas por segundo**, también se cuentan las llamadas internas a <xref:System.Net.HttpWebRequest.Abort%2A>. Estas llamadas internas suelen estar provocadas por tiempos de expiración que a una aplicación puede interesarle medir.  
  
 El contador de **HttpWebRequests con error por segundo** contiene el número de objetos <xref:System.Net.HttpWebRequest> que recibieron del servidor un código de estado de error por segundo. Esto significa que el código de estado recibido del servidor Http al final de la solicitud no se encontraba en el intervalo de 200 a 299. Los códigos de estado que se controlan y producen una nueva solicitud (por ejemplo, muchos de los códigos de estado 401 No autorizado) producirán o no un error en función del resultado del reintento. Si la aplicación ve un error basado en el reintento, este contador se incrementa.  
  
 Es posible acceder a los contadores de rendimiento de red y administrarlos mediante el <xref:System.Diagnostics.PerformanceCounter> y clases relacionadas del espacio de nombres <xref:System.Diagnostics>. Los contadores de rendimiento de red también se pueden ver con la consola del Monitor de rendimiento de Windows.  
  
 Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará. Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración. Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse. Para obtener más información, vea [ \<performanceCounter> elemento (configuración de red)](../configure-apps/file-schema/network/performancecounter-element-network-settings.md).  
  
 Si se habilitan los contadores de red, esto crearán y se actualizarán los contadores de rendimiento globales y por dominio de aplicación. Si deshabilita esta opción, la aplicación no proporcionará datos del contador de rendimiento de red.  
  
 Los contadores de rendimiento se agrupan en categorías. Una aplicación puede enumerar todas las categorías con el código de ejemplo siguiente:  
  
```csharp
PerformanceCounterCategory[] Array = PerformanceCounterCategory.GetCategories();  
for (int i = 0; i < Array.Length; i++)  
{  
    Console.Out.WriteLine("{0}. Name={1} Help={2}", i, Array[i].CategoryName, Array[i].CategoryHelp);  
}  
```  
  
 Los contadores de rendimiento de red se muestran en dos categorías:  
  
- «Redes de .NET CLR» - Los contadores de rendimiento originales introducidos en .NET Framework versión 2 y compatibles con .NET Framework versión 2 y posteriores.  
  
- «Redes de ".NET CLR 4.0.0.0» - Todos los contadores de socket anteriores más los nuevos contadores de rendimiento compatibles con .NET Framework versión 4 y versiones posteriores. Estos nuevos contadores proporcionan información de rendimiento sobre los objetos <xref:System.Net.HttpWebRequest>.  
  
 Para más información sobre el acceso y la administración de los contadores de rendimiento en una aplicación, vea [Contadores de rendimiento](performance-counters.md).  

## <a name="security-performance-counters"></a>Contadores de rendimiento de seguridad  
 La categoría de seguridad de .NET CLR de la consola de rendimiento incluye contadores de rendimiento que proporcionan información sobre las comprobaciones de seguridad que Common Language Runtime realiza para una aplicación. En la siguiente tabla se describen estos contadores de rendimiento.  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|**Número de comprobaciones del tiempo de vínculo**|Muestra el número total de comprobaciones de seguridad de acceso del código en tiempo de vínculo desde que se inició la aplicación. Las comprobaciones de seguridad de acceso del código en tiempo de vínculo se realizan cuando un llamador solicita un determinado permiso en tiempo de compilación Just-In-Time (JIT). Una comprobación en tiempo de vínculo se realiza una vez por cada llamador. Este recuento no indica problemas graves de rendimiento; simplemente indica la actividad del sistema de seguridad.|  
|**% de tiempo de comprobaciones RT**|Muestra el porcentaje de tiempo invertido en realizar comprobaciones de seguridad de acceso del código en tiempo de ejecución desde la última muestra. Este contador se actualiza al final de una comprobación de seguridad de .NET Framework. No es un promedio; representa el último valor observado.|  
|**% de tiempo autenticando firmas**|Reservado para uso futuro.|  
|**Profundidad del recorrido de la pila**|Muestra la profundidad de la pila durante esa última comprobación de seguridad de acceso del código en tiempo de ejecución. Las comprobaciones de seguridad de acceso del código en tiempo de ejecución se realizan recorriendo la pila. Este contador no es un promedio; solo muestra el último valor observado.|  
|**Número total de comprobaciones en tiempo de ejecución**|Muestra el número total de comprobaciones de seguridad de acceso del código en tiempo de ejecución realizadas desde que se inició la aplicación. Las comprobaciones de seguridad de acceso del código en tiempo de ejecución se realizan cuando un llamador solicita un determinado permiso. La comprobación en tiempo de ejecución se realiza en cada llamada del llamador y examina la pila del subproceso actual del llamador. Cuando se usa con el contador de **Profundidad del recorrido de la pila**, este contador indica la disminución del rendimiento que tiene lugar para las comprobaciones de seguridad.|  
  
## <a name="see-also"></a>Vea también

- [Contadores de rendimiento](performance-counters.md)
- [Generar perfiles en tiempo de ejecución](runtime-profiling.md)
