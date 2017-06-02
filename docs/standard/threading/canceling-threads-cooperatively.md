---
title: "Canceling Threads Cooperatively | Microsoft Docs"
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
  - "threads, cancellation"
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Canceling Threads Cooperatively
Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)],.NET Framework no ofrecía ningún medio integrado para cancelar un subproceso de forma cooperativa después de su inicio. Sin embargo, en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede utilizar tokens de cancelación para cancelar subprocesos, de la misma forma que puede utilizarlos para cancelar objetos <xref:System.Threading.Tasks.Task?displayProperty=fullName> o consultas PLINQ. Aunque la clase <xref:System.Threading.Thread?displayProperty=fullName> no ofrece compatibilidad integrada para tokens de cancelación, puede pasar un token a un procedimiento de subproceso con el constructor <xref:System.Threading.Thread> que toma un delegado <xref:System.Threading.ParameterizedThreadStart>. En el ejemplo siguiente se muestra cómo hacerlo:  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## Vea también  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)