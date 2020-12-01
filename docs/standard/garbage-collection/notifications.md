---
title: Notificaciones de recolección de elementos no utilizados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
ms.openlocfilehash: 70343851ba73af9041014e8654f5df82d8389c39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734782"
---
# <a name="garbage-collection-notifications"></a>Notificaciones de recolección de elementos no utilizados

Hay situaciones en que una colección de elementos no utilizados completa (es decir, una colección de generación 2) de Common Language Runtime puede afectar negativamente al rendimiento. Esto puede ser un problema especialmente con servidores que procesan grandes volúmenes de solicitudes; en este caso, una recolección grande de elementos no utilizados puede causar un tiempo de espera en la solicitud. Para evitar una recolección grande durante un período crítico, puede recibir una notificación de la proximidad de una recolección grande de elementos no utilizados y adoptar las medidas pertinentes para redirigir la carga de trabajo a otra instancia del servidor. También puede incluir una recolección por su cuenta, siempre que la instancia de servidor actual no necesite procesar solicitudes.  
  
 El método <xref:System.GC.RegisterForFullGCNotification%2A> registra una notificación que se genera si el tiempo de ejecución detecta que una recolección de elementos no utilizados completa está próxima. Esta notificación consta de dos partes: cuando se está aproximando la recolección de elementos no utilizados completa y cuando finaliza la recolección de elementos no utilizados completa.  
  
> [!WARNING]
> Solo las recolecciones de elementos no utilizados bloqueadas generarán notificaciones. Cuando el elemento de configuración [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) está habilitado, las recolecciones de elementos no utilizados en segundo plano no generarán notificaciones.  
  
 Para determinar cuándo se ha generado una notificación, use los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A>. Por lo general, utilice estos métodos en un bucle `while` para obtener continuamente una enumeración <xref:System.GCNotificationStatus> que muestra el estado de la notificación. Si el valor es <xref:System.GCNotificationStatus.Succeeded>, puede hacer lo siguiente:  
  
- En respuesta a una notificación obtenida con el método <xref:System.GC.WaitForFullGCApproach%2A>, puede redirigir la carga de trabajo y posiblemente inducir una recolección.  
  
- En respuesta a una notificación obtenida con el método <xref:System.GC.WaitForFullGCComplete%2A>, puede habilitar la instancia de servidor actual para volver a procesar las solicitudes. También puede recopilar información. Por ejemplo, puede usar el método <xref:System.GC.CollectionCount%2A> para registrar el número de recolecciones.  
  
 Los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> están diseñados para que funcionen de forma conjunta. Utilizar un método sin el otro puede producir resultados indeterminados.  
  
## <a name="full-garbage-collection"></a>Recolección de elementos no utilizados completa  

 El tiempo de ejecución produce una recolección de elementos no utilizados completa cuando se cumple alguna de las situaciones siguientes:  
  
- Se ha promocionado suficiente memoria en la generación 2 para generar la siguiente recolección de la generación 2.  
  
- Se ha promocionado suficiente memoria en el montón de objetos grandes para generar la siguiente recolección de la generación 2.  
  
- Una recolección de la generación 1 se escala a una recolección de la generación 2 debido a dos factores.  
  
 Los umbrales especificados en el método <xref:System.GC.RegisterForFullGCNotification%2A> se aplican a los dos primeros escenarios. Sin embargo, en el primer escenario no siempre recibirá la notificación en el tiempo proporcional a los valores de umbral especificados por dos motivos:  
  
- El tiempo de ejecución no comprueba cada asignación de objetos pequeños (por motivos de rendimiento).  
  
- Solo las recolecciones de la generación 1 promueven la memoria a la generación 2.  
  
 El tercer escenario también contribuye a la incertidumbre de cuándo recibirá la notificación. Aunque esto no es una garantía, demuestra ser útil para mitigar los efectos de una recolección de elementos no utilizados completa inoportuna redirigiendo las solicitudes durante este tiempo o induciendo la recolección por su cuenta cuando sea más apropiado.  
  
## <a name="notification-threshold-parameters"></a>Parámetros del umbral de notificación  

 El método <xref:System.GC.RegisterForFullGCNotification%2A> tiene dos parámetros para especificar los valores de umbral de los objetos de generación 2 y del montón de objetos grandes. Cuando se alcanza dichos valores, debe generarse una notificación de recolección de elementos no utilizados. En la siguiente tabla se describen estos parámetros.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Número comprendido entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos promocionados en la generación 2.|  
|`largeObjectHeapThreshold`|Un número comprendido entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos asignados en el montón de objetos grandes.|  
  
 Si especifica un valor que es demasiado alto, hay una alta probabilidad de recibir una notificación, pero podría producirse un tiempo de espera demasiado largo antes de que el tiempo de ejecución genere una recolección. Si induce una recolección, puede reclamar más objetos de los que reclamarían si el tiempo de ejecución genera la recolección.  
  
 Si especifica un valor que es demasiado bajo, el tiempo de ejecución puede provocar la recolección antes de que haya tenido tiempo suficiente para recibir la notificación.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  

 En el ejemplo siguiente, un grupo de solicitudes web entrantes del servicio de servidores. Para simular la carga de trabajo de procesamiento de solicitudes, se agregan matrices de bytes a una colección <xref:System.Collections.Generic.List%601>. Cada servidor registra una notificación de la recolección de elementos no utilizados y luego inicia un subproceso en el método del usuario `WaitForFullGCProc` para supervisar continuamente la enumeración <xref:System.GCNotificationStatus> devuelta por los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A>.  
  
 Los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> llaman a sus respectivos métodos de usuario de control de eventos cuando se emite una notificación:  
  
- `OnFullGCApproachNotify`  
  
     Este método llama al método de usuario `RedirectRequests`, que indica al servidor de puesta en cola de solicitudes que suspenda el envío de solicitudes al servidor. Esto se simula con la definición de la variable de nivel de clase `bAllocate` en `false`, para que no se asignen más objetos.  
  
     Después, se llama al método de usuario `FinishExistingRequests` para finalizar el procesamiento de las solicitudes de servidor pendientes. Esto se simula mediante la desactivación de la recolección <xref:System.Collections.Generic.List%601>.  
  
     Por último, se indujo una recolección de elementos no utilizados porque la carga de trabajo es ligera.  
  
- `OnFullGCCompleteNotify`  
  
     Este método llama al método de usuario `AcceptRequests` para reanudar la aceptación de solicitudes porque el servidor ya no es susceptible a una recolección de elementos no utilizados completa. Esta acción se simula estableciendo la variable `bAllocate` en `true`, para que se reanude la adición de los objetos a la recolección <xref:System.Collections.Generic.List%601>.  
  
 El código siguiente contiene el método `Main` del ejemplo.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 El siguiente código contiene el método de usuario `WaitForFullGCProc`, que incluye un bucle while continuo para comprobar las notificaciones de recolección de elementos no utilizados.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 El código siguiente contiene el método `OnFullGCApproachNotify` tras realizar la llamada al  
  
 Método `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 El código siguiente contiene el método `OnFullGCApproachComplete` tras realizar la llamada al  
  
 Método `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 El código siguiente contiene los métodos de usuario tras realizar la llamada a los métodos `OnFullGCApproachNotify` y `OnFullGCCompleteNotify`. Los métodos de usuario redirigen las solicitudes, finalizan las solicitudes existentes y reanudan las solicitudes después de que se produzca una recolección de elementos no utilizados completa.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 El ejemplo de código completo es el siguiente:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Recolección de elementos no utilizados](index.md)
