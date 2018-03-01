---
title: "Cómo: Realizar escuchas de varias solicitudes de cancelación"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 397de114a3d8c3cbcfbc8ab55e4dbaf45ca9b652
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="205bb-102">Cómo: Realizar escuchas de varias solicitudes de cancelación</span><span class="sxs-lookup"><span data-stu-id="205bb-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="205bb-103">En este ejemplo se muestra cómo escuchar dos tokens de cancelación simultáneamente, para poder cancelar una operación si el token lo solicita.</span><span class="sxs-lookup"><span data-stu-id="205bb-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="205bb-104">Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario".</span><span class="sxs-lookup"><span data-stu-id="205bb-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="205bb-105">Este error es benigno.</span><span class="sxs-lookup"><span data-stu-id="205bb-105">This error is benign.</span></span> <span data-ttu-id="205bb-106">Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="205bb-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="205bb-107">Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.</span><span class="sxs-lookup"><span data-stu-id="205bb-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="205bb-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="205bb-108">Example</span></span>  
 <span data-ttu-id="205bb-109">En el siguiente ejemplo, el método <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> se utiliza para combinar dos tokens en uno.</span><span class="sxs-lookup"><span data-stu-id="205bb-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="205bb-110">Esto permite que el token se pase a métodos que adoptan un token de cancelación como un argumento.</span><span class="sxs-lookup"><span data-stu-id="205bb-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="205bb-111">En el ejemplo se muestra un escenario común en el que un método debe observar un token pasado desde fuera de la clase y un token generado dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="205bb-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="205bb-112">Cuando el token vinculado produce una clase <xref:System.OperationCanceledException>, el token que se pasa a la excepción es el token vinculado, no uno de los tokens predecesores.</span><span class="sxs-lookup"><span data-stu-id="205bb-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="205bb-113">Para determinar cuál de los tokens se canceló, compruebe el estado de los tokens predecesores directamente.</span><span class="sxs-lookup"><span data-stu-id="205bb-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="205bb-114">En este ejemplo, <xref:System.AggregateException> nunca debería iniciarse, pero se detecta aquí porque en escenarios del mundo real cualquier otra excepción aparte de <xref:System.OperationCanceledException> producida a partir del delegado de tarea se encapsula en <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="205bb-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205bb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="205bb-115">See Also</span></span>  
 [<span data-ttu-id="205bb-116">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="205bb-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
