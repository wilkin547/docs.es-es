---
title: Subprocesos y subprocesamiento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b57cac34009e13c27c6d34a0ab402f9ecbe08305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="threads-and-threading"></a>Subprocesos y subprocesamiento
Sistemas operativos usan procesos para separar las distintas aplicaciones que se ejecutan. Los subprocesos son la unidad básica a la que el sistema operativo asigna tiempo de procesador y más de un subproceso puede ejecutar código dentro de ese proceso. Cada subproceso mantiene controladores de excepciones, una prioridad de programación y un conjunto de estructuras que el sistema usa para guardar el contexto del subproceso hasta que esté programada. El contexto del subproceso incluye toda la información que el subproceso necesita para reanudar sin problemas la ejecución, incluido el conjunto de registros de la CPU y la pila, en el espacio de direcciones del proceso de host del subproceso.  
  
 .NET Framework subdivide un proceso de sistema operativo en pequeños subprocesos administrados, denominados dominios de aplicación, representados por <xref:System.AppDomain?displayProperty=nameWithType>. Uno o varios subprocesos administrados (representados por <xref:System.Threading.Thread?displayProperty=nameWithType>) pueden ejecutarse en uno o varios de los dominios de aplicación dentro del mismo proceso administrado. Aunque cada dominio de aplicación se inicia con un único subproceso, el código en ese dominio de aplicación puede crear dominios de aplicación adicionales y subprocesos adicionales. El resultado es que un subproceso administrado puede moverse libremente entre dominios de aplicación dentro del mismo proceso administrado; es posible que tenga solo un subproceso que se moviera entre varios dominios de aplicación.  
  
 Un sistema operativo que admita multitarea preferente crea el efecto de ejecución simultánea de varios subprocesos desde varios procesos. Esto hace al dividir el tiempo de procesador disponible entre los subprocesos que lo necesitan, asignar un intervalo de tiempo de procesador para cada subproceso uno tras otro. El subproceso actualmente en ejecución se suspende cuando el tiempo que transcurre el intervalo y otro subproceso reanuda su ejecución. Cuando el sistema cambia de un subproceso a otro, guarda el contexto del subproceso del subproceso prioritario y vuelve a cargar el contexto del subproceso guardado del siguiente subproceso de la cola de subprocesos.  
  
 La longitud de la porción de tiempo depende del sistema operativo y el procesador. Dado que cada intervalo de tiempo es pequeño, varios subprocesos parecen que se ejecutan al mismo tiempo, incluso si hay un solo procesador. Esto es realmente el caso en sistemas multiprocesador, donde los subprocesos ejecutables se distribuyen entre los procesadores disponibles.  
  
## <a name="when-to-use-multiple-threads"></a>Cuándo utilizar varios subprocesos  
 Software que requiere la intervención del usuario debe reaccionar a las actividades del usuario, lo más rápidamente posible para proporcionar una experiencia de usuario enriquecida. Sin embargo, al mismo tiempo, debe hacer los cálculos necesarios para presentar los datos para el usuario lo más rápido posible. Si la aplicación utiliza sólo un subproceso de ejecución, puede combinar [programación asincrónica](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) con[comunicación remota de .NET Framework](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) o [servicios Web XML](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c) creado con ASP .NET para utilizar el tiempo de procesamiento de otros equipos, además de los suyos propios para aumentar la capacidad de respuesta para el usuario y se reduce el tiempo de procesamiento de datos de la aplicación. Si está realizando trabajo intensivo de entrada/salida, también puede usar los puertos de terminación de E/S para aumentar la capacidad de respuesta de la aplicación.  
  
### <a name="advantages-of-multiple-threads"></a>Ventajas de varios subprocesos  
 Sin embargo, se utiliza más de un subproceso, es la técnica más eficaz disponible para aumentar la capacidad de respuesta al usuario y procesar los datos necesarios para realizar el trabajo prácticamente al mismo tiempo. En un equipo con un procesador, varios subprocesos pueden crear este efecto, aprovechando los breves períodos de tiempo entre eventos de usuario para procesar los datos en segundo plano. Por ejemplo, un usuario puede editar una hoja de cálculo mientras otro subproceso se volverán a calcular otras partes de la hoja de cálculo dentro de la misma aplicación.  
  
 Sin modificación, la misma aplicación aumentaría drásticamente la satisfacción del usuario cuando se ejecuta en un equipo con más de un procesador. El único dominio de aplicación podría utilizar varios subprocesos para realizar las tareas siguientes:  
  
-   Comunicarse a través de una red, en un servidor Web y una base de datos.  
  
-   Realizar operaciones que requieren una gran cantidad de tiempo.  
  
-   Distinguir tareas de diversas prioridades. Por ejemplo, un subproceso de prioridad alta administra tareas críticas en el tiempo, y un subproceso de prioridad baja realiza otras tareas.  
  
-   Permitir que la interfaz de usuario siga respondiendo, mientras se asigna tiempo a tareas en segundo plano.  
  
### <a name="disadvantages-of-multiple-threads"></a>Desventajas de varios subprocesos  
 Se recomienda que utilice el menor número de subprocesos como sea posible, lo que minimiza el uso de recursos del sistema operativo y mejorar el rendimiento. Subprocesamiento también tiene requisitos de recursos y conflictos potenciales tenerse en cuenta al diseñar la aplicación. Los requisitos de recursos son los siguientes:  
  
-   El sistema utiliza memoria para la información de contexto requerida por procesos, **AppDomain** objetos y subprocesos. Por lo tanto, el número de procesos, **AppDomain** objetos y los subprocesos que se pueden crear está limitado por la memoria disponible.  
  
-   Mantener un seguimiento de un gran número de subprocesos, se consume tiempo de procesador significativo. Si hay demasiados subprocesos, la mayoría de ellos no realizará un progreso importante. Si la mayoría de los subprocesos actuales se encuentran en un proceso, los subprocesos de otros procesos se programan con menos frecuencia.  
  
-   Controlar la ejecución de código con muchos subprocesos es complejo y puede ser un origen de muchos errores.  
  
-   Destruir subprocesos requiere saber lo que podría suceder y controlar dichos problemas.  
  
 Proporciona acceso compartido a los recursos puede generar conflictos. Para evitar conflictos, debe sincronizar o controlar el acceso a los recursos compartidos. Si no se sincroniza el acceso correctamente (en los dominios de aplicación de la misma o distintas) puede causar problemas, como interbloqueos (en los que dos subprocesos dejan de responder mientras cada uno espera a que el otro se complete) y las condiciones de carrera (cuando se produce un resultado anómalo debido a una dependencia decisiva e inesperada de la duración de dos eventos). El sistema proporciona objetos de sincronización que pueden utilizarse para coordinar recursos compartidos entre varios subprocesos. Reducir el número de subprocesos resulta más fácil sincronizar recursos.  
  
 Los recursos que requieren sincronización incluyen:  
  
-   Recursos del sistema (por ejemplo, los puertos de comunicaciones).  
  
-   Recursos compartidos por varios procesos (por ejemplo, identificadores de archivo).  
  
-   Los recursos de un único dominio de aplicación (como globales, estáticos y campos de instancia) tengan acceso varios subprocesos.  
  
### <a name="threading-and-application-design"></a>Subprocesamiento y diseño de aplicaciones  
 En general, usando la <xref:System.Threading.ThreadPool> clase es la manera más fácil de controlar varios subprocesos para tareas relativamente cortas que no bloquearán otros subprocesos y cuando no se espera ninguna programación particular de las tareas. Sin embargo, hay una serie de motivos para crear sus propios subprocesos:  
  
-   Si necesita una tarea para que tenga una prioridad determinada.  
  
-   Si tiene una tarea que podría ejecutar mucho tiempo (y, por tanto, bloquear otras tareas).  
  
-   Si debe colocar los subprocesos en un contenedor uniproceso (todos los **ThreadPool** subprocesos están en el apartamento multiproceso).  
  
-   Si necesita una identidad estable asociada al subproceso. Por ejemplo, debe utilizar un subproceso dedicado para cancelar dicho subproceso, suspenderlo o detectarlo por nombre.  
  
-   Si tiene que ejecutar los subprocesos en segundo plano que interactúan con la interfaz de usuario, la versión 2.0 de .NET Framework proporciona un <xref:System.ComponentModel.BackgroundWorker> componente que se comunica mediante eventos, con el cálculo de referencias entre subprocesos al subproceso de interfaz de usuario.  
  
### <a name="threading-and-exceptions"></a>Subprocesamiento y excepciones  
 Control de excepciones en subprocesos. Las excepciones no controladas en subprocesos, incluso de fondo, generalmente finalizan el proceso. Hay tres excepciones de esta regla:  
  
-   A <xref:System.Threading.ThreadAbortException> se produce en un subproceso porque <xref:System.Threading.Thread.Abort%2A> se llamó.  
  
-   Un <xref:System.AppDomainUnloadedException> se produce en un subproceso porque se está descargando el dominio de aplicación.  
  
-   Common Language Runtime o un proceso de host finaliza el subproceso.  
  
 Para obtener más información, consulte [excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  En las versiones 1.0 y 1.1 de .NET Framework, common language runtime intercepta silenciosamente algunas excepciones, por ejemplo en el grupo de subprocesos. Esto puede dañar el estado de la aplicación y puede acabar haciendo que las aplicaciones no respondan, lo que podrían ser muy difíciles de depurar.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Sincronizar datos para subprocesamiento múltiple](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md) (Clase ThreadPool administrada)
