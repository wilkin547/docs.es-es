---
title: "Notificaciones de recolección de elementos no utilizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a>Notificaciones de recolección de elementos no utilizados
Hay situaciones en que una colección de elementos no utilizados completa (es decir, una recolección de generación 2) por common language runtime puede afectar negativamente al rendimiento. Esto puede ser un problema especialmente con servidores que procesan grandes volúmenes de solicitudes; en este caso, una recolección largo puede provocar un tiempo de espera de solicitud. Para evitar que una recolección completa de la que se producen durante un período crítico, puede recibir una notificación que una colección de elementos no utilizados completa se está aproximando a y, a continuación, tome medidas para redirigir la carga de trabajo a otra instancia del servidor. También puede inducir una recolección usted mismo, siempre que la instancia del servidor actual no es necesario procesar las solicitudes.  
  
 El <xref:System.GC.RegisterForFullGCNotification%2A> método registra una notificación que se genera si el tiempo de ejecución detecta que una recolección de elementos no utilizados completa está próxima. Esta notificación consta de dos partes: cuando se está aproximando la colección de elementos no utilizados completa y cuando ha completado la recolección de elementos no utilizados completa.  
  
> [!WARNING]
>  Colecciones de elementos no utilizados de bloqueo solo genera notificaciones. Cuando el [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) elemento de configuración está habilitado, las recolecciones de elementos no utilizados de fondo no generará notificaciones.  
  
 Para determinar cuándo se ha producido una notificación, utilice el <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos. Por lo general, utilice estos métodos en un `while` bucle continuamente obtener un <xref:System.GCNotificationStatus> enumeración que muestra el estado de la notificación. Si el valor es <xref:System.GCNotificationStatus.Succeeded>, puede hacer lo siguiente:  
  
-   En respuesta a una notificación obtenida con el <xref:System.GC.WaitForFullGCApproach%2A> método, puede redirigir la carga de trabajo y posiblemente inducir una recolección.  
  
-   En respuesta a una notificación obtenida con el <xref:System.GC.WaitForFullGCComplete%2A> método, hacer que la instancia del servidor actual disponible para procesar las solicitudes de nuevo. También puede recopilar información. Por ejemplo, puede usar el <xref:System.GC.CollectionCount%2A> método para registrar el número de colecciones.  
  
 El <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos están diseñados para trabajar conjuntamente. Utiliza un método sin el otro puede producirse resultados indeterminados.  
  
## <a name="full-garbage-collection"></a>Colección de elementos no utilizados completa  
 El tiempo de ejecución produce una recolección completa cuando se cumple alguna de las situaciones siguientes:  
  
-   Se ha promocionado suficiente memoria a la generación 2 para producir la recolección de generación 2 siguiente.  
  
-   Se ha promocionado suficiente memoria en el montón de objetos grandes para hacer que la recolección de generación 2 siguiente.  
  
-   Una recolección de generación 1 se remite a una recolección de generación 2 debido a otros factores.  
  
 Los umbrales que especifique en el <xref:System.GC.RegisterForFullGCNotification%2A> método se aplica a los dos primeros escenarios. Sin embargo, en el primer escenario no siempre recibirá la notificación en el tiempo proporcional a los valores de umbral especificados por dos motivos:  
  
-   El tiempo de ejecución no comprueba cada asignación de objetos pequeños (por motivos de rendimiento).  
  
-   Solo generación 1 colecciones promueven la memoria a la generación 2.  
  
 El tercer escenario también contribuye a la incertidumbre de cuando reciba la notificación. Aunque esto no es una garantía, siendo una forma útil de mitigar los efectos de una recolección completa inoportuno al redirigir las solicitudes durante este tiempo o induce la colección al que se puede incluir mejor.  
  
## <a name="notification-threshold-parameters"></a>Parámetros de umbral de notificación  
 El <xref:System.GC.RegisterForFullGCNotification%2A> método tiene dos parámetros para especificar los valores de umbral de los objetos de generación 2 y el montón de objetos grandes. Cuando se cumplen esos valores, debe emitirse una notificación de recolección. En la tabla siguiente se describe estos parámetros.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Un número entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos que se promocionan de la generación 2.|  
|`largeObjectHeapThreshold`|Un número entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos que se asignan en el montón de objetos grandes.|  
  
 Si especifica un valor que es demasiado alto, hay una alta probabilidad de que recibirá una notificación, pero podría ser demasiado un período de espera antes de que el tiempo de ejecución hace que una colección. Si induce una colección, puede reclamar más objetos que se reclame si el tiempo de ejecución hace que la colección.  
  
 Si especifica un valor que es demasiado bajo, el tiempo de ejecución puede provocar la colección antes de que haya tiempo suficiente para recibir una notificación.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente, un grupo de servidores de servicio de las solicitudes Web entrantes. Para simular la carga de trabajo de procesamiento de solicitudes, matrices de bytes se agregan a un <xref:System.Collections.Generic.List%601> colección. Cada servidor se registra para una notificación de la colección de elementos no utilizados y, a continuación, inicia un subproceso en el `WaitForFullGCProc` método de usuario para supervisar continuamente el <xref:System.GCNotificationStatus> enumeración devuelto por la <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos.  
  
 El <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos llamar a sus respectivos métodos de usuario de control de eventos cuando se produce una notificación:  
  
-   `OnFullGCApproachNotify`  
  
     Este método llama a la `RedirectRequests` método de usuario, que indica al servidor de puesta en cola de solicitud para suspender el envío de solicitudes al servidor. Esto se simula estableciendo la variable de nivel de clase `bAllocate` a `false` para que no hay más objetos se asignan.  
  
     Después, el `FinishExistingRequests` se denomina método de usuario para finalizar el procesamiento de las solicitudes del servidor pendientes. Esto se simula desactivando el <xref:System.Collections.Generic.List%601> colección.  
  
     Por último, se indujo una recolección porque la carga de trabajo está claro.  
  
-   `OnFullGCCompleteNotify`  
  
     Este método llama al método de usuario `AcceptRequests` para reanudar la aceptación de solicitudes porque el servidor ya no es susceptible a una colección de elementos no utilizados completa. Esta acción se simula estableciendo la `bAllocate` variable `true` para que pueden reanudar objetos que se va a agregar a la <xref:System.Collections.Generic.List%601> colección.  
  
 El siguiente código contiene la `Main` método del ejemplo.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 El siguiente código contiene la `WaitForFullGCProc` método de usuario, que contiene un bucle while continuo para comprobar las notificaciones de recopilación de elementos no utilizados.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 El siguiente código contiene la `OnFullGCApproachNotify` método cuando llame desde el  
  
 Método `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 El siguiente código contiene la `OnFullGCApproachComplete` método cuando llame desde el  
  
 Método `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 El código siguiente contiene los métodos de usuario que se llaman desde el `OnFullGCApproachNotify` y `OnFullGCCompleteNotify` métodos. Los métodos de usuario redirigirán las solicitudes, finalizan las solicitudes existentes y, a continuación, reanudan las solicitudes después de que se ha producido una colección de elementos no utilizados completa.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 El ejemplo de código completo es como sigue:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Recolección de elementos no utilizados](../../../docs/standard/garbage-collection/index.md)
