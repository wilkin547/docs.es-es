---
title: "Garbage Collection Notifications | Microsoft Docs"
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
  - "garbage collection, notifications"
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Garbage Collection Notifications
Hay situaciones en las que una recolección de elementos no utilizados completa \(es decir, una recolección de generación 2\) por Common Language Runtime puede afectar negativamente al rendimiento.  Esto puede suponer un problema, sobre todo con los servidores que procesan grandes volúmenes de solicitudes; en este caso, una recolección de elementos no utilizados de larga duración puede dar lugar a que se agote el tiempo de espera de la solicitud.  Para evitar que se produzca una recolección de elementos no utilizados completa en un momento crítico, existe la posibilidad de recibir una notificación de que se va a producir en breve dicha recolección de modo que se podrá redirigir la carga de trabajo a otra instancia del servidor.  También se puede inducir una recolección, siempre que la instancia del servidor actual no necesite procesar solicitudes.  
  
 El método <xref:System.GC.RegisterForFullGCNotification%2A> se registra para que se cree una notificación cuando el motor en tiempo de ejecución perciba que se aproxima una recolección de elementos no utilizados completa.  Esta notificación consta de dos partes: la parte en la que se indica cuándo se aproxima la recolección de elementos no utilizados completa y la parte en la que se indica cuándo se completa dicha recolección.  
  
> [!WARNING]
>  Sólo bloqueando recolecciones de elementos no utilizados active las notificaciones.  Cuando se habilita el elemento de configuración de [\<gcConcurrent\>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) , las recolecciones de elementos no utilizados en segundo plano no iniciará notificaciones.  
  
 Para determinar cuándo se genera una notificación, utilice los métodos <xref:System.GC.WaitForFullGCComplete%2A> y <xref:System.GC.WaitForFullGCApproach%2A>.  Normalmente, estos métodos se utilizan en un bucle `while` para obtener una enumeración <xref:System.GCNotificationStatus> sin interrupciones que muestre el estado de la notificación.  Si ese valor es <xref:System.GCNotificationStatus>, puede hacer lo siguiente:  
  
-   En respuesta a una notificación obtenida con el método <xref:System.GC.WaitForFullGCApproach%2A>, puede redirigir la carga de trabajo y posiblemente inducir por sí mismo una recolección.  
  
-   En respuesta a una notificación obtenida con el método <xref:System.GC.WaitForFullGCComplete%2A>, puede habilitar la instancia del servidor actual para que procese las solicitudes de nuevo.  También puede recopilar información.  Por ejemplo, puede utilizar el método <xref:System.GC.CollectionCount%2A> para registrar el número de recolecciones.  
  
 Los métodos <xref:System.GC.WaitForFullGCComplete%2A> y <xref:System.GC.WaitForFullGCApproach%2A> están diseñados para trabajar juntos.  Si se utiliza un método sin el otro pueden producirse resultados indeterminados.  
  
## Recolección de elementos no utilizados completa  
 El motor en tiempo de ejecución desencadena una recolección de elementos no utilizados completa en las situaciones siguientes:  
  
-   Se ha promovido bastante cantidad de memoria a la generación 2 para producir la recolección de generación 2 siguiente.  
  
-   Se ha promovido una gran cantidad de memoria a un montón de objetos grandes para desencadenar la recolección de generación 2 siguiente.  
  
-   Una recolección de generación 1 se ha elevado a una recolección de generación 2 por otros factores.  
  
 Los umbrales que especifique en el método <xref:System.GC.RegisterForFullGCNotification%2A> se aplicarán en los dos primeros escenarios.  Sin embargo, en el primer escenario, no siempre recibirá la notificación en el tiempo proporcional a los valores de umbral que especificó por dos motivos:  
  
-   El motor en tiempo de ejecución no comprueba cada asignación de objetos pequeños \(por motivos de rendimiento\).  
  
-   Solo las recolecciones de generación 1 promueven la memoria a la generación 2.  
  
 El tercer escenario también contribuye a la incertidumbre respecto a cuándo se recibirá la notificación.  Aunque no es una garantía, demuestra que es un mecanismo útil para mitigar los efectos de una recolección de elementos no utilizados completa inoportuna al redirigir las solicitudes durante este período de tiempo o al inducir por sí mismo la recolección cuando puede resultar más oportuna.  
  
## Parámetros de umbral de notificación  
 El método <xref:System.GC.RegisterForFullGCNotification%2A> tiene dos parámetros para especificar los valores de umbral de los objetos de generación 2 y el montón de objetos grandes.  Cuando estos valores se satisfacen, deberá emitirse una notificación de recolección de elementos no utilizados.  En la tabla siguiente se describen estos parámetros.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`maxGenerationThreshold`|Número comprendido entre 1 y 99 que especifica cuándo debe emitirse la notificación conforme a los objetos promovidos a la generación 2.|  
|`largeObjectHeapThreshold`|Número comprendido entre 1 y 99 que especifica cuándo debe emitirse la notificación conforme a los objetos asignados al montón de objetos grandes.|  
  
 Si especifica un valor demasiado alto, existe una gran probabilidad de que reciba una notificación, pero es posible que tenga que esperar largo tiempo antes de que el motor en tiempo de ejecución produzca la recolección.  Si induce la recolección por sí mismo, puede reclamar más objetos de los que reclamaría si el motor en tiempo de ejecución desencadenara la recolección.  
  
 Si especifica un valor demasiado bajo, el motor en tiempo de ejecución puede desencadenar la recolección antes de tener suficiente tiempo para emitir una notificación.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente, un grupo de servidores da servicio a solicitudes web entrantes.  Para simular la carga de trabajo del procesamiento de las solicitudes, las matrices de bytes se agregan a una colección <xref:System.Collections.Generic.List%601>.  Cada servidor realiza el registro de una notificación de recolección de elementos no utilizados y, a continuación, inicia un subproceso en el método de usuario `WaitForFullGCProc` para supervisar de forma continuada la enumeración <xref:System.GCNotificationStatus> devuelta por los métodos <xref:System.GC.WaitForFullGCComplete%2A> y <xref:System.GC.WaitForFullGCApproach%2A>.  
  
 Los métodos <xref:System.GC.WaitForFullGCComplete%2A> y <xref:System.GC.WaitForFullGCApproach%2A> llaman a sus respectivos métodos de usuario de control de eventos cuando se emite una notificación:  
  
-   `OnFullGCApproachNotify`  
  
     Este método llama al método de usuario `RedirectRequests`, que indica al servidor de cola de solicitudes que deje de enviar solicitudes al servidor.  Esto se simula al establecer la variable `bAllocate` de nivel de clase en `false` para que no se asignen más objetos.  
  
     A continuación, se llama al método de usuario `FinishExistingRequests` para finalizar el procesamiento de las solicitudes del servidor pendientes.  Para simular esto, se borra la colección <xref:System.Collections.Generic.List%601>.  
  
     Finalmente, se induce una recolección de elementos no utilizados porque la carga de trabajo es ligera.  
  
-   `OnFullGCCompleteNotify`  
  
     Este método llama al método de usuario `AcceptRequests` para reanudar la aceptación de solicitudes, pues el servidor ya no es susceptible de que se produzca una recolección de elementos no utilizados completa.  Esta acción se simula estableciendo la variable `bAllocate` en `true` para que los objetos puedan agregarse de nuevo a la colección <xref:System.Collections.Generic.List%601>.  
  
 El código siguiente contiene el método `Main` del ejemplo.  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 El código siguiente contiene el método de usuario `WaitForFullGCProc`, que contiene un bucle while continuo para comprobar las notificaciones de la recolección de elementos no utilizados.  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 El código siguiente contiene el método `OnFullGCApproachNotify` cuando se llama desde el  
  
 Método `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 El código siguiente contiene el método `OnFullGCApproachComplete` cuando se llama desde el  
  
 Método `WaitForFullGCProc`.  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 El código siguiente contiene los métodos de usuario a los que se llama desde los métodos `OnFullGCCompleteNotify` y `OnFullGCApproachNotify`.  Los métodos de usuario redirigen las solicitudes, finalizan las solicitudes existentes y, a continuación, reanudan las solicitudes una vez que tiene lugar la recolección de elementos no utilizados completa.  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 El ejemplo de código completo es el siguiente:  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## Vea también  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)