---
description: 'Más información acerca de cómo: declarar eventos personalizados para evitar bloqueos (Visual Basic)'
title: Procedimiento para declarar eventos personalizados para evitar bloqueos
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: a4ad3162e8f95ebbf7567d427ea00060b19b2235
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100469726"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="b8ef7-103">Cómo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8ef7-103">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>

<span data-ttu-id="b8ef7-104">Hay varias circunstancias en las que es importante que un controlador de eventos no bloquee los controladores de eventos subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-104">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="b8ef7-105">Los eventos personalizados permiten que el evento llame a sus controladores de eventos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-105">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="b8ef7-106">De forma predeterminada, el campo de almacenamiento de copia de seguridad de una declaración de evento es un delegado de multidifusión que combina en serie todos los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-106">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="b8ef7-107">Esto significa que si un controlador tarda mucho tiempo en completarse, bloquea los demás controladores hasta que se completa.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-107">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="b8ef7-108">(Los controladores de eventos bien comprobables nunca deben realizar operaciones largas o de bloqueo).</span><span class="sxs-lookup"><span data-stu-id="b8ef7-108">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="b8ef7-109">En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar un evento personalizado para ejecutar los controladores de eventos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-109">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8ef7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8ef7-110">Example</span></span>  

 <span data-ttu-id="b8ef7-111">En este ejemplo, el `AddHandler` descriptor de acceso agrega el delegado de cada controlador del `Click` evento a un <xref:System.Collections.ArrayList> almacenado en el `EventHandlerList` campo.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-111">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="b8ef7-112">Cuando el código genera el `Click` evento, el `RaiseEvent` descriptor de acceso invoca de forma asincrónica todos los delegados de controlador de eventos utilizando el <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-112">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="b8ef7-113">Ese método invoca cada controlador en un subproceso de trabajo y vuelve inmediatamente, por lo que los controladores no pueden bloquearse entre sí.</span><span class="sxs-lookup"><span data-stu-id="b8ef7-113">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#27)]  
  
## <a name="see-also"></a><span data-ttu-id="b8ef7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8ef7-114">See also</span></span>

- <xref:System.Collections.ArrayList>
- <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>
- [<span data-ttu-id="b8ef7-115">Eventos</span><span class="sxs-lookup"><span data-stu-id="b8ef7-115">Events</span></span>](index.md)
- [<span data-ttu-id="b8ef7-116">Cómo: Declarar eventos personalizados para conservar memoria</span><span class="sxs-lookup"><span data-stu-id="b8ef7-116">How to: Declare Custom Events To Conserve Memory</span></span>](how-to-declare-custom-events-to-conserve-memory.md)
