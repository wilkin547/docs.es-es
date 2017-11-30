---
title: "Cómo: Realizar escuchas de solicitudes mediante sondeo"
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="bc0cd-102">Cómo: Realizar escuchas de solicitudes mediante sondeo</span><span class="sxs-lookup"><span data-stu-id="bc0cd-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="bc0cd-103">En el ejemplo siguiente se muestra una manera de que el código de usuario puede sondear un token de cancelación a intervalos regulares para ver si se ha solicitado la cancelación desde el subproceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="bc0cd-104">Este ejemplo se utiliza la <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo, pero el mismo patrón se aplica a las operaciones asincrónicas creadas directamente por el <xref:System.Threading.ThreadPool?displayProperty=nameWithType> tipo o el <xref:System.Threading.Thread?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc0cd-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc0cd-105">Example</span></span>  
 <span data-ttu-id="bc0cd-106">El sondeo necesita algún tipo de bucle o código recursivo que periódicamente se puede leer el valor booleano <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="bc0cd-107">Si usas el <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> tipo y está esperando la tarea se complete en el subproceso que realiza la llamada, puede usar el <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> método para comprobar la propiedad y producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="bc0cd-108">Con este método, se asegura de que se produce la excepción correcta en respuesta a una solicitud.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="bc0cd-109">Si usas un <xref:System.Threading.Tasks.Task>, a continuación, llamar a este método es mejor que iniciar manualmente una <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="bc0cd-110">Si no tiene que producir la excepción, puede comprobar la propiedad y volver del método si la propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="bc0cd-111">Una llamada a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> es muy rápido y no presenta una sobrecarga significativa en bucles.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="bc0cd-112">Si se está llamando a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, solo tiene que comprobar explícitamente la <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> propiedad si tiene otro trabajo pendiente en respuesta a la cancelación además de producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="bc0cd-113">En este ejemplo, puede ver que el código realmente tiene acceso a la propiedad dos veces: una vez en el acceso explícito y de nuevo en el <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="bc0cd-114">Sin embargo, dado el hecho de leer el <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> propiedad implica volátil solo una instrucción por acceso de lectura, el acceso de doble no es importante desde la perspectiva del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="bc0cd-115">Es preferible al llamar al método en lugar de producir manualmente la <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="bc0cd-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0cd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc0cd-116">See Also</span></span>  
 [<span data-ttu-id="bc0cd-117">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="bc0cd-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
