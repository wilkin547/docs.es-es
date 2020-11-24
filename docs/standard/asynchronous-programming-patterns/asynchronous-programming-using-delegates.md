---
title: Programación asincrónica mediante delegados
ms.date: 03/30/2017
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
ms.openlocfilehash: da468d3b16ee504317c7de2e216a9be2073d1cf3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830511"
---
# <a name="asynchronous-programming-using-delegates"></a><span data-ttu-id="f2139-102">Programación asincrónica mediante delegados</span><span class="sxs-lookup"><span data-stu-id="f2139-102">Asynchronous Programming Using Delegates</span></span>

<span data-ttu-id="f2139-103">Los delegados permiten llamar a métodos sincrónicos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f2139-103">Delegates enable you to call a synchronous method in an asynchronous manner.</span></span> <span data-ttu-id="f2139-104">Cuando se llama a un delegado sincrónicamente, el método `Invoke` llama al método de destino directamente en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f2139-104">When you call a delegate synchronously, the `Invoke` method calls the target method directly on the current thread.</span></span> <span data-ttu-id="f2139-105">Si se llama al método `BeginInvoke`, Common Language Runtime (CLR) coloca la solicitud en cola y devuelve inmediatamente el control al elemento que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="f2139-105">If the `BeginInvoke` method is called, the common language runtime (CLR) queues the request and returns immediately to the caller.</span></span> <span data-ttu-id="f2139-106">El método de destino se llama asincrónicamente desde un subproceso del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f2139-106">The target method is called asynchronously on a thread from the thread pool.</span></span> <span data-ttu-id="f2139-107">El subproceso original, que envió la solicitud, puede continuar ejecutándose en paralelo con el método de destino.</span><span class="sxs-lookup"><span data-stu-id="f2139-107">The original thread, which submitted the request, is free to continue executing in parallel with the target method.</span></span> <span data-ttu-id="f2139-108">Si se ha especificado un método de devolución de llamada en la llamada al método `BeginInvoke`, el método de devolución de llamada se llama cuando finaliza el método de destino.</span><span class="sxs-lookup"><span data-stu-id="f2139-108">If a callback method has been specified in the call to the `BeginInvoke` method, the callback method is called when the target method ends.</span></span> <span data-ttu-id="f2139-109">En el método de devolución de llamada, el método `EndInvoke` obtiene el valor devuelto y cualquier parámetro de entrada y salida o de solo salida.</span><span class="sxs-lookup"><span data-stu-id="f2139-109">In the callback method, the `EndInvoke` method obtains the return value and any input/output or output-only parameters.</span></span> <span data-ttu-id="f2139-110">Si no se especifica ningún método de devolución de llamada al llamar a `BeginInvoke`, se puede llamar a `EndInvoke` desde el subproceso que llamó a `BeginInvoke`.</span><span class="sxs-lookup"><span data-stu-id="f2139-110">If no callback method is specified when calling `BeginInvoke`, `EndInvoke` can be called from the thread that called `BeginInvoke`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f2139-111">Los compiladores deben emitir clases de delegados con los métodos `Invoke`, `BeginInvoke` y `EndInvoke` mediante la firma de delegados que especifique el usuario.</span><span class="sxs-lookup"><span data-stu-id="f2139-111">Compilers should emit delegate classes with `Invoke`, `BeginInvoke`, and `EndInvoke` methods using the delegate signature specified by the user.</span></span> <span data-ttu-id="f2139-112">Los métodos `BeginInvoke` y `EndInvoke` deben representarse como nativos.</span><span class="sxs-lookup"><span data-stu-id="f2139-112">The `BeginInvoke` and `EndInvoke` methods should be decorated as native.</span></span> <span data-ttu-id="f2139-113">Debido a que estos métodos están marcados como nativos, Common Language Runtime proporciona automáticamente la implementación en el momento en que se carga la clase.</span><span class="sxs-lookup"><span data-stu-id="f2139-113">Because these methods are marked as native, the CLR automatically provides the implementation at class load time.</span></span> <span data-ttu-id="f2139-114">El cargador se asegura de que no se reemplazarán.</span><span class="sxs-lookup"><span data-stu-id="f2139-114">The loader ensures that they are not overridden.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2139-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f2139-115">In This Section</span></span>  
 [<span data-ttu-id="f2139-116">Llamada a métodos sincrónicos de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="f2139-116">Calling Synchronous Methods Asynchronously</span></span>](calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="f2139-117">Describe el uso de los delegados para realizar llamadas asincrónicas a métodos ordinarios y proporciona ejemplos de código sencillos en los que se muestran los cuatro mecanismos que existen para esperar a que una llamada asincrónica devuelva datos.</span><span class="sxs-lookup"><span data-stu-id="f2139-117">Discusses the use of delegates to make asynchronous calls to ordinary methods, and provides simple code examples that show the four ways to wait for an asynchronous call to return.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f2139-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f2139-118">Related Sections</span></span>  
 [<span data-ttu-id="f2139-119">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="f2139-119">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="f2139-120">Se describe la programación asincrónica en .NET.</span><span class="sxs-lookup"><span data-stu-id="f2139-120">Describes asynchronous programming in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2139-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2139-121">See also</span></span>

- <xref:System.Delegate>
