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
ms.openlocfilehash: 36de18e976401dd0cde878852c064aa982b8acde
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188502"
---
# <a name="canceling-threads-cooperatively"></a><span data-ttu-id="e4f58-102">Cancelación de subprocesos de manera cooperativa</span><span class="sxs-lookup"><span data-stu-id="e4f58-102">Canceling threads cooperatively</span></span>

<span data-ttu-id="e4f58-103">Antes de .NET Framework 4, .NET no ofrecía ninguna forma integrada de cancelar un subproceso de forma cooperativa después de su inicio.</span><span class="sxs-lookup"><span data-stu-id="e4f58-103">Prior to .NET Framework 4, .NET provided no built-in way to cancel a thread cooperatively after it was started.</span></span> <span data-ttu-id="e4f58-104">Pero a partir de .NET Framework 4, puede usar <xref:System.Threading.CancellationToken?displayProperty=nameWithType> para cancelar subprocesos, de la misma forma que puede utilizarlos para cancelar objetos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o consultas PLINQ.</span><span class="sxs-lookup"><span data-stu-id="e4f58-104">However, starting with .NET Framework 4, you can use a <xref:System.Threading.CancellationToken?displayProperty=nameWithType> to cancel threads, just as you can use them to cancel <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or PLINQ queries.</span></span> <span data-ttu-id="e4f58-105">Aunque la clase <xref:System.Threading.Thread?displayProperty=nameWithType> no ofrece compatibilidad integrada para tokens de cancelación, puede pasar un token a un procedimiento de subproceso con el constructor <xref:System.Threading.Thread> que toma un delegado <xref:System.Threading.ParameterizedThreadStart> .</span><span class="sxs-lookup"><span data-stu-id="e4f58-105">Although the <xref:System.Threading.Thread?displayProperty=nameWithType> class does not offer built-in support for cancellation tokens, you can pass a token to a thread procedure by using the <xref:System.Threading.Thread> constructor that takes a <xref:System.Threading.ParameterizedThreadStart> delegate.</span></span> <span data-ttu-id="e4f58-106">En el ejemplo siguiente se muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="e4f58-106">The following example demonstrates how to do this.</span></span>  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="e4f58-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4f58-107">See also</span></span>

- [<span data-ttu-id="e4f58-108">Usar subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="e4f58-108">Using Threads and Threading</span></span>](using-threads-and-threading.md)
