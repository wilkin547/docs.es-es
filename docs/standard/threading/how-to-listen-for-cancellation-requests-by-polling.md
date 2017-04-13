---
title: "How to: Listen for Cancellation Requests by Polling | Microsoft Docs"
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
  - "cancellation, how to poll for requests"
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Listen for Cancellation Requests by Polling
En el ejemplo siguiente se muestra una manera en que el código de usuario puede sondear un token de cancelación a intervalos periódicos para ver si el subproceso que realiza la llamada ha solicitado la cancelación.  En este ejemplo se usa el tipo <xref:System.Threading.Tasks.Task?displayProperty=fullName>, pero el mismo modelo es aplicable a las operaciones asincrónicas creadas directamente por el tipo <xref:System.Threading.ThreadPool?displayProperty=fullName> o <xref:System.Threading.Thread?displayProperty=fullName>.  
  
## Ejemplo  
 El sondeo necesita algún tipo de bucle o código recursivo que pueda leer periódicamente el valor de la propiedad booleana <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>.  Si está usando el tipo <xref:System.Threading.Tasks.Task?displayProperty=fullName> y espera que la tarea se complete en el subproceso que realiza la llamada, puede emplear el método <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> para comprobar la propiedad y producir la excepción.  Mediante este método, se asegura de que se produce la excepción correcta como respuesta a una solicitud.  Si está usando <xref:System.Threading.Tasks.Task>, es mejor llamar a este método que producir manualmente una excepción <xref:System.OperationCanceledException>.  Si no tiene que producir la excepción, simplemente puede comprobar la propiedad y volver del método si la propiedad es `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 La llamada a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> es sumamente rápida y no presenta una gran sobrecarga en los bucles.  
  
 Si está llamando a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, solo tiene que comprobar explícitamente la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> si tiene que hacer otro trabajo como respuesta a la cancelación además de producir la excepción.  En este ejemplo, puede ver que el código realmente tiene acceso dos veces a la propiedad: una vez en el acceso explícito y de nuevo en el método <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>.  Pero puesto que el acto de leer la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> implica solo una instrucción de lectura volátil por acceso, el acceso doble no es significativo desde una perspectiva de rendimiento.  Sigue siendo preferible llamar al método en lugar de producir manualmente <xref:System.OperationCanceledException>.  
  
## Vea también  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)