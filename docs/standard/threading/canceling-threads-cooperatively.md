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
helpviewer_keywords: threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 482f48b347af1a4f76231abcb15abc2f4dba168b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="canceling-threads-cooperatively"></a>Cancelar subprocesos de manera cooperativa
Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)],.NET Framework no ofrecía ningún medio integrado para cancelar un subproceso de forma cooperativa después de su inicio. Sin embargo, en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede utilizar tokens de cancelación para cancelar subprocesos, tal y como se puede utilizar para cancelar <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objetos o consultas PLINQ. Aunque la <xref:System.Threading.Thread?displayProperty=nameWithType> clase no ofrece compatibilidad integrada para tokens de cancelación, puede pasar un token a un procedimiento de subproceso mediante la <xref:System.Threading.Thread> constructor que toma un <xref:System.Threading.ParameterizedThreadStart> delegar. En el ejemplo siguiente se muestra cómo hacerlo:  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>Vea también  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)
