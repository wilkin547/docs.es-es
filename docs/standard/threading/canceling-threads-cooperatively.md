---
title: Cancelar subprocesos de manera cooperativa
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
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 334cbcf8b4a888dbac5962c0fd668673e15e0e29
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="canceling-threads-cooperatively"></a>Cancelar subprocesos de manera cooperativa
Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)],.NET Framework no ofrecía ningún medio integrado para cancelar un subproceso de forma cooperativa después de su inicio. Sin embargo, en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede utilizar tokens de cancelación para cancelar subprocesos, de la misma forma que puede utilizarlos para cancelar objetos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o consultas PLINQ. Aunque la clase <xref:System.Threading.Thread?displayProperty=nameWithType> no ofrece compatibilidad integrada para tokens de cancelación, puede pasar un token a un procedimiento de subproceso con el constructor <xref:System.Threading.Thread> que toma un delegado <xref:System.Threading.ParameterizedThreadStart>. En el ejemplo siguiente se muestra cómo hacerlo:  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Vea también  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)
