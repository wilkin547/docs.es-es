---
title: Cancelación de subprocesos de manera cooperativa
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd32deb9c8719a12b76aaea8ec91a17471cf18f9
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259865"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="9a58b-102">Cancelación de subprocesos de manera cooperativa</span><span class="sxs-lookup"><span data-stu-id="9a58b-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="9a58b-103">Antes de .NET Framework 4, .NET Framework no ofrecía ningún medio integrado para cancelar un subproceso de forma cooperativa después de su inicio.</span><span class="sxs-lookup"><span data-stu-id="9a58b-103">Prior to the .NET Framework 4, the .NET Framework provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="9a58b-104">Pero a partir de .NET Framework 4, puede usar <xref:System.Threading.CancellationToken?displayProperty=nameWithType> para cancelar subprocesos, de la misma forma que puede utilizarlos para cancelar objetos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o consultas PLINQ.</span><span class="sxs-lookup"><span data-stu-id="9a58b-104">However, starting with the .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="9a58b-105">Aunque la clase <xref:System.Threading.Thread?displayProperty=nameWithType> no ofrece compatibilidad integrada para tokens de cancelación, puede pasar un token a un procedimiento de subproceso con el constructor <xref:System.Threading.Thread> que toma un delegado <xref:System.Threading.ParameterizedThreadStart>.</span><span class="sxs-lookup"><span data-stu-id="9a58b-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="9a58b-106">En el ejemplo siguiente se muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="9a58b-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="9a58b-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a58b-107">See also</span></span>

- [<span data-ttu-id="9a58b-108">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="9a58b-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
