---
title: "Threads and Threading | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "multiple threads"
  - "threading [.NET Framework]"
  - "threading [.NET Framework], multiple threads"
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Threads and Threading
Los sistemas operativos utilizan procesos para independizar las diferentes aplicaciones que ejecutan.  Los subprocesos son la unidad básica a la que el sistema operativo asigna tiempo de procesador. Puede que haya más de un subproceso ejecutando código dentro del proceso.  Cada subproceso mantiene controladores de excepciones, una prioridad de programación y un conjunto de estructuras que el sistema utiliza para guardar el contexto del subproceso hasta que se programe.  El contexto del subproceso incluye, en el espacio de direcciones del proceso host del subproceso, toda la información que necesita éste para reanudar sin problemas la ejecución, como el conjunto de registros de la CPU y la pila.  
  
 .NET Framework subdivide un proceso de sistema operativo en pequeños subprocesos administrados, denominados dominios de aplicación y representados por <xref:System.AppDomain?displayProperty=fullName>.  Dentro del mismo proceso administrado se pueden ejecutar uno o varios subprocesos administrados \(representados por <xref:System.Threading.Thread?displayProperty=fullName>\) en uno o varios dominios de aplicación.  Aunque cada dominio de aplicación se inicia con un único subproceso, su código puede crear otros dominios de aplicación y subprocesos adicionales.  El resultado es que un subproceso administrado puede moverse libremente entre dominios de aplicación dentro del mismo proceso administrado; podría tener sólo un subproceso que se moviera entre varios dominios de aplicación.  
  
 Un sistema operativo que admita multitareas prioritarias crea el efecto de ejecución simultánea de varios subprocesos desde varios procesos.  Para ello, se divide el tiempo de procesador disponible entre los subprocesos que lo necesitan y se asigna un espacio de tiempo de procesador a cada subproceso, uno tras otro.  Cuando trascurre su espacio de tiempo, el subproceso que se esté ejecutando actualmente se suspende y otro subproceso reanuda su ejecución.  Cuando el sistema cambia de un subproceso a otro, guarda el contexto del subproceso prioritario y vuelve a cargar el contexto de subproceso guardado del siguiente subproceso de la cola.  
  
 El espacio de tiempo asignado depende del sistema operativo y del procesador.  Puesto que cada espacio de tiempo es pequeño, parece que se ejecutan varios subprocesos a la vez, incluso si hay un único procesador.  De hecho, éste es el caso en sistemas multiprocesador, donde los subprocesos ejecutables se distribuyen entre los procesadores disponibles.  
  
## Cuándo utilizar varios subprocesos  
 El software que requiere la interacción del usuario debe reaccionar a sus actividades lo más rápido posible para que la sensación del usuario ante el sistema sea satisfactoria.  No obstante, al mismo tiempo, debe realizar los cálculos necesarios para presentarle los datos tan rápido como sea posible.  Si una aplicación utiliza sólo un subproceso de ejecución, puede combinar la [programación asincrónica](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) con [comunicación remota de .NET Framework](http://msdn.microsoft.com/es-es/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) o con [servicios Web XML](http://msdn.microsoft.com/es-es/1e64af78-d705-4384-b08d-591a45f4379c) creados mediante ASP.NET para utilizar el tiempo de procesamiento de otros equipos, además del de su propio equipo, y aumentar la capacidad de respuesta al usuario a la vez que se reduce el tiempo de procesamiento de los datos de la aplicación.  Si está realizando un trabajo intenso de entrada y salida, también puede utilizar los puertos de finalización de E\/S para aumentar la capacidad de respuesta de la aplicación.  
  
### Ventajas del uso de varios subprocesos  
 No obstante, el uso de más de un subproceso es la técnica más eficaz disponible para elevar la capacidad de respuesta al usuario y procesar los datos requeridos al realizar el trabajo prácticamente al mismo tiempo.  En un equipo con un procesador, varios subprocesos pueden crear este efecto si aprovechan los breves períodos entre los eventos de usuario para procesar los datos en segundo plano.  Por ejemplo, un usuario puede modificar una hoja de cálculo mientras otro subproceso vuelve a calcular otras partes de la hoja de cálculo dentro de la misma aplicación.  
  
 La misma aplicación, sin modificación, aumentaría considerablemente el grado de satisfacción del usuario si se ejecutara en un equipo con más de un procesador.  Su único dominio de aplicación podría utilizar varios subprocesos para realizar las siguientes tareas:  
  
-   Comunicarse a través de una red, con un servidor Web y una base de datos.  
  
-   Realizar operaciones que requieren una gran cantidad de tiempo.  
  
-   Distinguir tareas de diversas prioridades.  Por ejemplo, un subproceso de prioridad alta administra tareas en las que el tiempo es decisivo y un proceso de prioridad baja realiza otras tareas.  
  
-   Permitir a la interfaz de usuario que siga respondiendo, mientras se asigna tiempo a las tareas en segundo plano.  
  
### Desventajas del uso de varios subprocesos  
 Se recomienda utilizar el menor número de subprocesos posible, puesto que de este modo se reduce el uso de recursos del sistema operativo y se mejora el rendimiento.  Al diseñar la aplicación, el subprocesamiento debe tener en cuenta los requisitos de recursos y conflictos potenciales.  Los requisitos de recursos son los siguientes:  
  
-   El sistema utiliza memoria para la información de contexto requerida por los procesos, objetos **AppDomain** y subprocesos.  Por tanto, el número de procesos, objetos **AppDomain** y subprocesos que se pueden crear está limitado por la memoria disponible.  
  
-   Si se realiza un seguimiento de un gran número de subprocesos, se utiliza una gran cantidad de tiempo de procesador.  Si hay demasiados subprocesos, la mayoría no avanzarán de forma significativa.  Si la mayor parte de los subprocesos actuales pertenecen a un proceso, los subprocesos de otros procesos se programan con menor frecuencia.  
  
-   El control de la ejecución del código con muchos subprocesos es complejo y puede constituir una fuente de muchos errores.  
  
-   Para destruir los subprocesos es necesario conocer lo que podría suceder y controlar dichos problemas.  
  
 Si se proporciona acceso compartido a los recursos, se pueden producir conflictos.  Para evitar los conflictos, es necesario sincronizar o controlar el acceso a los recursos compartidos.  Si no se sincroniza el acceso correctamente \(en los mismos dominios de aplicación o en otros\) se pueden producir problemas como interbloqueos \(en los que dos subprocesos dejan de responder mientras cada uno espera a que el otro se complete\) y condiciones de carrera \(cuando se produce un resultado anómalo debido a una dependencia decisiva e inesperada de la duración de dos eventos\).  El sistema proporciona objetos de sincronización que pueden utilizarse para coordinar recursos compartidos entre varios subprocesos.  Si se reduce el número de subprocesos, se facilita la sincronización de los recursos.  
  
 Entre los recursos que requieren sincronización se incluyen los siguientes:  
  
-   Recursos del sistema \(como puertos de comunicaciones\).  
  
-   Recursos compartidos por varios procesadores \(como identificadores de archivo\).  
  
-   Los recursos de un único dominio de aplicación \(como campos globales, estáticos y de instancia\) a los que tienen acceso varios subprocesos.  
  
### Subprocesamiento y diseño de aplicaciones  
 En general, el uso de la clase <xref:System.Threading.ThreadPool> es la forma más fácil de controlar varios subprocesos para tareas relativamente cortas que no bloquearán otros subprocesos y cuando no se espera ninguna programación particular de las tareas.  No obstante, hay diversos motivos para crear sus propios subprocesos:  
  
-   Si es necesario que una tarea tenga una prioridad en particular.  
  
-   Si tiene una tarea que podría ejecutarse durante bastante tiempo \(y, por tanto, bloquear otras tareas\).  
  
-   Si debe ubicar subprocesos en un contenedor uniproceso \(todos los subprocesos **ThreadPool** se encuentran en un contenedor multiproceso\).  
  
-   Si necesita asociar una identidad estable al subproceso.  Por ejemplo, debería utilizar un subproceso dedicado para anular dicho subproceso, suspenderlo o detectarlo por nombre.  
  
-   Si es necesario ejecutar subprocesos de fondo que interactúan con la interfaz de usuario, la versión 2.0 de .NET Framework proporciona un componente <xref:System.ComponentModel.BackgroundWorker> que se comunica utilizando eventos, con cálculo de referencias entre subprocesos al subproceso de la interfaz de usuario.  
  
### Subprocesamiento y excepciones  
 Controle las excepciones en subprocesos.  Las excepciones no controladas en subprocesos, incluso los subprocesos de fondo, generalmente finalizan el proceso.  Hay tres excepciones a esta regla:  
  
-   Se produce una excepción <xref:System.Threading.ThreadAbortException> en un subproceso porque se llamó a <xref:System.Threading.Thread.Abort%2A>.  
  
-   Se produce una excepción <xref:System.AppDomainUnloadedException> en un subproceso, porque se descarga el dominio de aplicación.  
  
-   Common Language Runtime o un proceso de host finaliza el subproceso.  
  
 Para obtener más información, vea [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  En las versiones 1.0 y 1.1 de .NET Framework, Common Language Runtime intercepta silenciosamente algunas excepciones, como por ejemplo en subprocesos ThreadPool.  Esto puede dañar el estado de la aplicación y hacer que en el futuro las aplicaciones no respondan, lo que podría ser muy difícil de depurar.  
  
## Vea también  
 <xref:System.Threading.ThreadPool>   
 <xref:System.ComponentModel.BackgroundWorker>   
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)   
 [The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md)