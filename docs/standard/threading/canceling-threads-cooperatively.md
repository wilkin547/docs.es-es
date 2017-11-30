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
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="ad480-102">Cancelar subprocesos de manera cooperativa</span><span class="sxs-lookup"><span data-stu-id="ad480-102">Canceling Threads Cooperatively</span></span>
<span data-ttu-id="ad480-103">Antes de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)],.NET Framework no ofrecía ningún medio integrado para cancelar un subproceso de forma cooperativa después de su inicio.</span><span class="sxs-lookup"><span data-stu-id="ad480-103">Prior to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="ad480-104">Sin embargo, en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede utilizar tokens de cancelación para cancelar subprocesos, tal y como se puede utilizar para cancelar <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objetos o consultas PLINQ.</span><span class="sxs-lookup"><span data-stu-id="ad480-104">However, in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use cancellation tokens to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="ad480-105">Aunque la <xref:System.Threading.Thread?displayProperty=nameWithType> clase no ofrece compatibilidad integrada para tokens de cancelación, puede pasar un token a un procedimiento de subproceso mediante la <xref:System.Threading.Thread> constructor que toma un <xref:System.Threading.ParameterizedThreadStart> delegar.</span><span class="sxs-lookup"><span data-stu-id="ad480-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="ad480-106">En el ejemplo siguiente se muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="ad480-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="ad480-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad480-107">See Also</span></span>  
 [<span data-ttu-id="ad480-108">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="ad480-108">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
