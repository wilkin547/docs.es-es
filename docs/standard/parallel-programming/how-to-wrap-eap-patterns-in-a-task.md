---
title: 'Cómo: Encapsular modelos de EAP en una tarea'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: ac7436892c644340286bb4670bf75c9cd63a8ce5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106823"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="d8e2c-102">Cómo: Encapsular modelos de EAP en una tarea</span><span class="sxs-lookup"><span data-stu-id="d8e2c-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="d8e2c-103">En el ejemplo siguiente se muestra cómo exponer una secuencia arbitraria de operaciones de modelo asincrónico basado en eventos (EAP) como una tarea mediante el uso de una clase <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span><span class="sxs-lookup"><span data-stu-id="d8e2c-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="d8e2c-104">En el ejemplo también se muestra cómo usar una clase <xref:System.Threading.CancellationToken> para invocar los métodos de cancelación integrados en los objetos <xref:System.Net.WebClient>.</span><span class="sxs-lookup"><span data-stu-id="d8e2c-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8e2c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8e2c-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="d8e2c-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8e2c-106">See also</span></span>

- [<span data-ttu-id="d8e2c-107">TPL y la programación asincrónica tradicional de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d8e2c-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
