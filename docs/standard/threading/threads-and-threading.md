---
title: Subprocesos y subprocesamiento
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4380c509a08ebe59f9561a9e6fc596458768917f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="threads-and-threading"></a>Subprocesos y subprocesamiento
Los sistemas operativos usan procesos para separar las distintas aplicaciones que ejecutan. Los subprocesos son la unidad básica a la que el sistema operativo asigna tiempo de procesador, y más de un subproceso puede ejecutar código dentro de ese proceso. Cada subproceso mantiene controladores de excepciones, una prioridad de programación y un conjunto de estructuras que el sistema usa para guardar el contexto del subproceso hasta que esté programado. El contexto del subproceso incluye toda la información que el subproceso necesita para reanudar sin problemas la ejecución, incluido el conjunto de pila y registros de CPU del subproceso, en el espacio de direcciones del proceso de host del subproceso.  
  
 .NET Framework subdivide un proceso de sistema operativo en subprocesos administrados ligeros, denominados dominios de aplicación, representados por <xref:System.AppDomain?displayProperty=nameWithType>. Uno o varios subprocesos administrados (representados por <xref:System.Threading.Thread?displayProperty=nameWithType>) pueden ejecutarse en uno o varios de los dominios de aplicación dentro del mismo proceso administrado. Aunque cada dominio de aplicación se inicia con un único subproceso, el código en ese dominio de aplicación puede crear dominios de aplicación adicionales y subprocesos adicionales. El resultado es que un subproceso administrado puede moverse libremente entre dominios de aplicación dentro del mismo proceso administrado; es posible que solo un subproceso se mueva entre varios dominios de aplicación.  
  
 Un sistema operativo que admita multitarea preferente crea el efecto de ejecución simultánea de varios subprocesos desde varios procesos. Esto se hace al dividir el tiempo de procesador disponible entre los subprocesos que lo necesitan, asignando un intervalo de tiempo de procesador a cada subproceso uno tras otro. El subproceso actualmente en ejecución se suspende cuando el período de tiempo transcurre y otro subproceso reanuda su ejecución. Cuando el sistema cambia de un subproceso a otro, guarda el contexto del subproceso del subproceso prioritario y vuelve a cargar el contexto del subproceso guardado del siguiente subproceso en la cola de subprocesos.  
  
 La duración del período de tiempo depende del sistema operativo y del procesador. Dado que cada intervalo de tiempo es pequeño, varios subprocesos parecen ejecutarse al mismo tiempo, aunque solo haya un procesador. Este es realmente el caso en sistemas multiprocesador, donde los subprocesos ejecutables se distribuyen entre los procesadores disponibles.  
  
## <a name="when-to-use-multiple-threads"></a>Cuándo utilizar varios subprocesos  
 El software que requiere la intervención del usuario debe reaccionar a las actividades del usuario lo más rápidamente posible para proporcionar una experiencia de usuario enriquecida. Sin embargo, al mismo tiempo, debe hacer los cálculos necesarios para presentar los datos al usuario lo más rápido posible. Si la aplicación utiliza solo un subproceso de ejecución, puede combinar la [programación asincrónica](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) con la [comunicación remota de .NET Framework](https://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) o los [servicios web XML](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c) creados con ASP .NET para utilizar el tiempo de procesamiento de otros equipos, además de los suyos propios, a fin de aumentar la capacidad de respuesta al usuario y reducir el tiempo de procesamiento de datos de la aplicación. Si está realizando trabajo intensivo de entrada/salida, también puede usar los puertos de terminación de E/S para aumentar la capacidad de respuesta de la aplicación.  
  
### <a name="advantages-of-multiple-threads"></a>Ventajas de varios subprocesos  
 Sin embargo, utilizar más de un subproceso es la técnica más eficaz disponible para aumentar la capacidad de respuesta al usuario y procesar los datos necesarios para realizar el trabajo prácticamente al mismo tiempo. En un equipo con un procesador, varios subprocesos pueden crear este efecto, aprovechando los breves períodos de tiempo entre eventos de usuario para procesar los datos en segundo plano. Por ejemplo, un usuario puede editar una hoja de cálculo mientras otro subproceso vuelve a calcular otras partes de la hoja de cálculo dentro de la misma aplicación.  
  
 Sin modificación, la misma aplicación aumentaría drásticamente la satisfacción del usuario cuando se ejecuta en un equipo con más de un procesador. El único dominio de aplicación podría utilizar varios subprocesos para realizar las tareas siguientes:  
  
-   Comunicarse a través de una red con un servidor web y una base de datos.  
  
-   Realizar operaciones que requieren una gran cantidad de tiempo.  
  
-   Distinguir tareas de diversas prioridades. Por ejemplo, un subproceso de prioridad alta administra tareas críticas en el tiempo, y un subproceso de prioridad baja realiza otras tareas.  
  
-   Permitir que la interfaz de usuario siga respondiendo, mientras se asigna tiempo a tareas en segundo plano.  
  
### <a name="disadvantages-of-multiple-threads"></a>Desventajas de varios subprocesos  
 Se recomienda que utilice el menor número de subprocesos posibles, lo que minimiza el uso de recursos del sistema operativo y mejora el rendimiento. Los subprocesos también tienen requisitos de recursos y plantean conflictos potenciales que deben tenerse en cuenta al diseñar la aplicación. Los requisitos de recursos son los siguientes:  
  
-   El sistema utiliza memoria para la información de contexto requerida por procesos, objetos **AppDomain** y subprocesos. Por lo tanto, el número de procesos, objetos **AppDomain** y subprocesos que se pueden crear está limitado por la memoria disponible.  
  
-   Realizar un seguimiento de un número elevado de subprocesos consume un tiempo de procesador significativo. Si hay demasiados subprocesos, la mayoría de ellos no progresará significativamente. Si la mayoría de los subprocesos actuales se encuentran en un proceso, los subprocesos de otros procesos se programan con menos frecuencia.  
  
-   Controlar la ejecución de código con muchos subprocesos es complicado y puede ser el origen de muchos errores.  
  
-   Destruir subprocesos requiere saber lo que podría suceder y controlar dichos problemas.  
  
 Proporcionar acceso compartido a los recursos puede generar conflictos. Para evitar conflictos, debe sincronizar los recursos compartidos o controlar el acceso a ellos. Si no se sincroniza el acceso correctamente (en los mismos dominios de aplicación o en dominios de aplicación diferentes), se pueden producir problemas como interbloqueos (en los que los dos subprocesos dejan de responder mientras cada uno espera a que el otro se complete) y condiciones de carrera (cuando se genera un resultado anómalo por una dependencia crítica inesperada de los intervalos de los dos eventos). El sistema proporciona objetos de sincronización que pueden utilizarse para coordinar recursos compartidos entre varios subprocesos. Reducir el número de subprocesos resulta más fácil para sincronizar recursos.  
  
 Los recursos que requieren sincronización incluyen:  
  
-   Recursos del sistema (por ejemplo, los puertos de comunicaciones).  
  
-   Recursos compartidos por varios procesos (por ejemplo, identificadores de archivo).  
  
-   Los recursos de un único dominio de aplicación (como campos globales, estáticos y de instancia) a los que acceden varios subprocesos.  
  
### <a name="threading-and-application-design"></a>Subprocesos y diseño de la aplicación  
 En general, usar la clase <xref:System.Threading.ThreadPool> es la manera más fácil de controlar varios subprocesos para tareas relativamente cortas que no bloquearán otros subprocesos y cuando no se espera ninguna programación particular de las tareas. Sin embargo, hay una serie de motivos para crear sus propios subprocesos:  
  
-   Si necesita que una tarea tenga una prioridad determinada.  
  
-   Si tiene una tarea que podría ejecutarse durante mucho tiempo y, en consecuencia, bloquea otras tareas.  
  
-   Si debe colocar los subprocesos en un contenedor uniproceso (todos los subprocesos **ThreadPool** están en el contenedor multiproceso).  
  
-   Si necesita una identidad estable asociada al subproceso. Por ejemplo, debe usar un subproceso dedicado para abortar dicho subproceso, suspenderlo o detectarlo por su nombre.  
  
-   Si necesita ejecutar subprocesos en segundo plano que interactúan con la interfaz de usuario, .NET Framework 2.0 proporciona un componente <xref:System.ComponentModel.BackgroundWorker> que se comunica mediante eventos, con serialización entre subprocesos, al subproceso de interfaz de usuario.  
  
### <a name="threading-and-exceptions"></a>Subprocesos y excepciones  
 Controle las excepciones de los subprocesos. Las excepciones no controladas de los subprocesos, incluso los subprocesos en segundo plano, generalmente finalizan el proceso. Hay tres excepciones de esta regla:  
  
-   Se genera <xref:System.Threading.ThreadAbortException> en un subproceso, porque se llamó a <xref:System.Threading.Thread.Abort%2A>.  
  
-   Se genera <xref:System.AppDomainUnloadedException> en un subproceso, porque se está descargando el dominio de aplicación.  
  
-   Common Language Runtime o un proceso de host finaliza el subproceso.  
  
 Para más información, consulte [Excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  En las versiones 1.0 y 1.1 de .NET Framework, Common Language Runtime intercepta silenciosamente algunas excepciones, por ejemplo, en los subprocesos del grupo de subprocesos. Esto puede dañar el estado de la aplicación y puede acabar haciendo que las aplicaciones no respondan, lo cual puede ser muy difícil de depurar.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Sincronizar datos para subprocesamiento múltiple](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md) (Clase ThreadPool administrada)
