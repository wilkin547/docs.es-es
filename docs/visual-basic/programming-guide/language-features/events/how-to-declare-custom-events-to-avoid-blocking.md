---
title: 'Cómo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 3cb66aed71195d2fd2335fbd59cc499b3dbf808e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646931"
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a><span data-ttu-id="c0514-102">Cómo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0514-102">How to: Declare Custom Events To Avoid Blocking (Visual Basic)</span></span>
<span data-ttu-id="c0514-103">Hay varias circunstancias cuando es importante que un controlador de eventos no se bloqueará siguientes controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="c0514-103">There are several circumstances when it is important that one event handler not block subsequent event handlers.</span></span> <span data-ttu-id="c0514-104">Los eventos personalizados permiten el evento llamar a sus controladores de eventos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c0514-104">Custom events allow the event to call its event handlers asynchronously.</span></span>  
  
 <span data-ttu-id="c0514-105">De forma predeterminada, el campo de almacén de respaldo de una declaración de evento es un delegado multidifusión que combina de forma consecutiva todos los controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="c0514-105">By default, the backing-store field for an event declaration is a multicast delegate that serially combines all the event handlers.</span></span> <span data-ttu-id="c0514-106">Esto significa que si un controlador tarda mucho tiempo en completarse, bloquea los demás controladores hasta que se complete.</span><span class="sxs-lookup"><span data-stu-id="c0514-106">This means that if one handler takes a long time to complete, it blocks the other handlers until it completes.</span></span> <span data-ttu-id="c0514-107">(Controladores de eventos con buen comportamiento nunca deben realizar las operaciones largas o puede producir bloqueos.)</span><span class="sxs-lookup"><span data-stu-id="c0514-107">(Well-behaved event handlers should never perform lengthy or potentially blocking operations.)</span></span>  
  
 <span data-ttu-id="c0514-108">En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar un evento personalizado para ejecutar los controladores de eventos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="c0514-108">Instead of using the default implementation of events that Visual Basic provides, you can use a custom event to execute the event handlers asynchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0514-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0514-109">Example</span></span>  
 <span data-ttu-id="c0514-110">En este ejemplo, el `AddHandler` descriptor de acceso agrega el delegado para cada controlador de la `Click` eventos a una <xref:System.Collections.ArrayList> almacenados en los `EventHandlerList` campo.</span><span class="sxs-lookup"><span data-stu-id="c0514-110">In this example, the `AddHandler` accessor adds the delegate for each handler of the `Click` event to an <xref:System.Collections.ArrayList> stored in the `EventHandlerList` field.</span></span>  
  
 <span data-ttu-id="c0514-111">Cuando el código genera el `Click` eventos, el `RaiseEvent` descriptor de acceso invoca todos los delegados de controlador de eventos asincrónicamente mediante el <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c0514-111">When code raises the `Click` event, the `RaiseEvent` accessor invokes all the event handler delegates asynchronously using the <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> method.</span></span> <span data-ttu-id="c0514-112">Ese método invoca cada controlador en un subproceso de trabajo y devuelve inmediatamente, por lo que no pueden bloquear controladores entre sí.</span><span class="sxs-lookup"><span data-stu-id="c0514-112">That method invokes each handler on a worker thread and returns immediately, so handlers cannot block one another.</span></span>  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c0514-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0514-113">See Also</span></span>  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [<span data-ttu-id="c0514-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="c0514-114">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="c0514-115">Declarar eventos personalizados para conservar memoria</span><span class="sxs-lookup"><span data-stu-id="c0514-115">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
