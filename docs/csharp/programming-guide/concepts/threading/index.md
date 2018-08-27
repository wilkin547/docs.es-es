---
title: Subprocesamiento (C#)
ms.date: 07/20/2015
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
ms.openlocfilehash: 35f0ee3bfd67104d9eaab7c4dde7e35a28a374c5
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934706"
---
# <a name="threading-c"></a>Subprocesamiento (C#)
El subprocesamiento permite a los programas de C# llevar a cabo un procesamiento simultáneo para que pueda hacer más de una operación a la vez. Por ejemplo, puede usar el subprocesamiento para hacer un seguimiento de los datos escritos por un usuario, realizar tareas en segundo plano y administrar transmisiones simultáneas de los datos escritos.  
  
 Los subprocesos tienen las propiedades siguientes:  
  
-   Permiten que un programa realice procesos simultáneos.  
  
-   El espacio de nombres <xref:System.Threading> de .NET Framework permite usar subprocesos con más facilidad.  
  
-   Comparten los recursos de una aplicación. Para obtener más información, vea [Using Threads and Threading](../../../../../docs/standard/threading/using-threads-and-threading.md) (Uso de subprocesos y subprocesamiento).  
  
 De forma predeterminada, un programa de C# contiene un subproceso. Sin embargo, se pueden crear y usar subprocesos auxiliares para ejecutar código en paralelo con el subproceso principal. Estos subprocesos se denominan a menudo *subprocesos de trabajo*.  
  
 Los subprocesos de trabajo se pueden usar para realizar tareas urgentes o que requieren mucho tiempo sin limitar el subproceso principal. Por ejemplo, los subprocesos de trabajo se usan a menudo en aplicaciones de servidor para procesar las solicitudes entrantes sin tener que esperar a que se complete una solicitud anterior. También se suelen usar para realizar tareas “en segundo plano” en aplicaciones de escritorio para que el subproceso principal, que dirige los elementos de la interfaz de usuario, siga respondiendo a las acciones del usuario.  
  
 El subprocesamiento resuelve los problemas de rendimiento y capacidad de respuesta, pero al hacerlo también puede crear problemas al compartir recursos, como interbloqueos y condiciones de carrera. Usar varios subprocesos es mejor en el caso de las tareas que requieren recursos distintos, como identificadores de archivos y conexiones de red. Al asignar varios subprocesos a un único recurso, es probable que se produzcan problemas de sincronización, y el hecho de que los subprocesos se bloqueen a menudo al esperar por otros subprocesos iría en contra de la finalidad de usar varios subprocesos.  
  
 Una estrategia habitual es usar subprocesos de trabajo para llevar a cabo tareas urgentes o que requieren mucho tiempo pero no necesitan muchos de los recursos usados por otros subprocesos. Naturalmente, hay varios subprocesos que deben acceder a algunos recursos de su programa. Para estos casos, el espacio de nombres <xref:System.Threading> proporciona clases para sincronizar subprocesos. Entre estas clases se encuentran <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent>.  
  
 Puede usar todas estas clases o solo algunas de ellas para sincronizar las actividades de varios subprocesos, pero el lenguaje C# proporciona una parte de compatibilidad con los subprocesos. Por ejemplo, una [instrucción lock](../../../../csharp/language-reference/keywords/lock-statement.md) proporciona características de sincronización mediante el uso implícito de <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  Empezando por [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], la programación multiproceso se simplifica significativamente con las clases <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), clases de colecciones simultáneas nuevas en el espacio de nombres <xref:System.Collections.Concurrent?displayProperty=nameWithType> y un nuevo modelo de programación basado en el concepto de tareas en lugar de subprocesos. Para más información, consulte [Parallel Programming](../../../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Sincronización de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)|Describe cómo controlar las interacciones de los subprocesos.|  
|[Subprocesamiento](../../../../../docs/standard/threading/index.md)|Describe cómo implementar subprocesamientos en .NET Framework.|
