---
title: "How to: Listen for Cancellation Requests That Have Wait Handles | Microsoft Docs"
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
  - "cancellation, waiting with wait handles"
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Listen for Cancellation Requests That Have Wait Handles
Si se bloquea un método mientras está esperando la señalización de un evento, no puede comprobar el valor del token de cancelación y responder a tiempo.  En el primer ejemplo se muestra cómo resolver este problema cuando está trabajando con eventos como <xref:System.Threading.ManualResetEvent?displayProperty=fullName> que no admiten el marco de cancelación unificada de forma nativa.  En el segundo ejemplo se muestra un enfoque más sencillo que usa <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>, que admite cancelación unificada.  
  
> [!NOTE]
>  Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno.  Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en los ejemplos siguientes.  Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" bajo **Herramientas, Opciones, Depuración, General**.  
  
## Ejemplo  
 En el ejemplo siguiente se usa <xref:System.Threading.ManualResetEvent> para mostrar cómo desbloquear identificadores de espera que no admiten cancelación unificada.  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## Ejemplo  
 En el ejemplo siguiente se usa <xref:System.Threading.ManualResetEventSlim> para mostrar cómo desbloquear primitivas de coordinación que admiten cancelación unificada.  Se puede usar el mismo enfoque con otras primitivas de coordinación ligeras, como <xref:System.Threading.Semaphore>`Slim` y <xref:System.Threading.CountdownEvent>.  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## Vea también  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)