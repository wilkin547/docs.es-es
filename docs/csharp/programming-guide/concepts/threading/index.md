---
title: Subprocesamiento (C#) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e3f213b43c2f05a5afef1db7aec8b9c2695df989
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---
# <a name="threading-c"></a>Subprocesamiento (C#)
Subprocesamiento permite que el programa de C# realizar el procesamiento simultáneo, por lo que puede hacer más de una operación a la vez. Por ejemplo, puede utilizar el subprocesamiento para supervisar la entrada del usuario, realizar tareas en segundo plano y controlar los flujos de entrada simultáneos.  
  
 Subprocesos tienen las siguientes propiedades:  
  
-   Subprocesos permiten al programa realizar el procesamiento simultáneo.  
  
-   .NET Framework <xref:System.Threading> dificulta el espacio de nombres uso subprocesos más fácil.  
  
-   Los subprocesos comparten recursos de la aplicación. Para obtener más información, consulte [utilizar subprocesos y subprocesamiento](https://msdn.microsoft.com/library/e1dx6b2h).  
  
 De forma predeterminada, un programa de C# tiene un subproceso. Sin embargo, subprocesos auxiliares se puede crear y usar para ejecutar código en paralelo con el subproceso principal. Estos subprocesos se denominan a menudo *subprocesos de trabajo*.  
  
 Subprocesos de trabajo se pueden utilizar para realizar tareas que consumen muchos recursos o crítico en el tiempo sin acaparar el subproceso principal. Por ejemplo, subprocesos de trabajo se utilizan a menudo en aplicaciones de servidor para atender las solicitudes entrantes sin tener que esperar para que se completó la solicitud anterior. Subprocesos de trabajo también se usan para realizar tareas "en segundo plano" en aplicaciones de escritorio para que el subproceso principal, lo que reduce los elementos de la interfaz de usuario, siga respondiendo a las acciones del usuario.  
  
 Los subprocesos resuelven los problemas de rendimiento y capacidad de respuesta, pero también pueden presentar problemas de uso compartido de recursos, como interbloqueos y condiciones de carrera. Varios subprocesos son más adecuados para las tareas que requieren recursos diferentes, como identificadores de archivos y conexiones de red. Asignar varios subprocesos a un único recurso es probable que se produzcan problemas de sincronización y tener subprocesos bloqueados con frecuencia cuando se espera otros subprocesos invalida el propósito del uso de varios subprocesos.  
  
 Una estrategia habitual consiste en utilizar subprocesos de trabajo para realizar mucho tiempo o tareas críticas en el tiempo que no requieren muchos de los recursos utilizados por otros subprocesos. Naturalmente, algunos recursos del programa deben tener acceso varios subprocesos. Para estos casos, la <xref:System.Threading> espacio de nombres proporciona clases para la sincronización de subprocesos. Estas clases incluyen <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent>, y <xref:System.Threading.ManualResetEvent>.  
  
 Puede usar algunas o todas estas clases para sincronizar las actividades de varios subprocesos, pero cierta compatibilidad para el subprocesamiento es compatible con el lenguaje C#. Por ejemplo, el [Lock (instrucción)](../../../../csharp/language-reference/keywords/lock-statement.md) proporciona características de sincronización a través del uso implícito de <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  A partir del [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], se simplifica enormemente la programación multiproceso con el <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> y <xref:System.Threading.Tasks.Task?displayProperty=fullName> clases, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), clases de colección simultánea nuevo en el <xref:System.Collections.Concurrent?displayProperty=fullName> espacio de nombres y un nuevo modelo de programación que se basa en el concepto de tareas en lugar de subprocesos. Para más información, consulte [Parallel Programming](https://msdn.microsoft.com/library/dd460693) (Programación en paralelo).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Aplicaciones multiproceso (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)|Describe cómo crear y utilizar subprocesos.|  
|[Parámetros y valores devueltos para procedimientos multiproceso (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|Describe cómo pasar y devolver parámetros con aplicaciones multiproceso.|  
|[Tutorial: Multithreading con el componente BackgroundWorker (C#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|Muestra cómo crear una sencilla aplicación multiproceso.|  
|[Sincronización de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)|Describe cómo controlar las interacciones de subprocesos.|  
|[Temporizadores de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md)|Describe cómo ejecutar procedimientos en subprocesos independientes a intervalos fijos.|  
|[Subprocesos de agrupación (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)|Describe cómo usar un grupo de subprocesos de trabajo administrados por el sistema.|  
|[Cómo: usar un grupo de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|Muestra el uso sincronizado de varios subprocesos en el grupo de subprocesos.|  
|[Subprocesamiento](https://msdn.microsoft.com/library/3e8s7xdd)|Describe cómo implementar los subprocesos en .NET Framework.|
