---
title: 'Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: d19c91d66e458ca2317dc049d517b92fa7406ef6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647211"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="08426-102">Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08426-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="08426-103">Hay varias circunstancias cuando es importante que una aplicación mantener el uso de memoria baja.</span><span class="sxs-lookup"><span data-stu-id="08426-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="08426-104">Eventos personalizados que la aplicación pueda utilizar memoria sólo para los eventos que administra.</span><span class="sxs-lookup"><span data-stu-id="08426-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="08426-105">De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo almacenar la información del evento.</span><span class="sxs-lookup"><span data-stu-id="08426-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="08426-106">Si una clase tiene muchos eventos no usados, innecesariamente ocupan memoria.</span><span class="sxs-lookup"><span data-stu-id="08426-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="08426-107">En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar eventos personalizados para administrar el uso de memoria más detenidamente.</span><span class="sxs-lookup"><span data-stu-id="08426-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08426-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="08426-108">Example</span></span>  
 <span data-ttu-id="08426-109">En este ejemplo, la clase utiliza una instancia de la <xref:System.ComponentModel.EventHandlerList> (clase), almacenado en el `Events` campo para almacenar información sobre los eventos en uso.</span><span class="sxs-lookup"><span data-stu-id="08426-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="08426-110">El <xref:System.ComponentModel.EventHandlerList> es una clase de lista optimizada diseñada para contener delegados.</span><span class="sxs-lookup"><span data-stu-id="08426-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="08426-111">Todos los eventos de la clase usan el `Events` campo para realizar un seguimiento de qué métodos está controlando cada evento.</span><span class="sxs-lookup"><span data-stu-id="08426-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="08426-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="08426-112">See Also</span></span>  
 <xref:System.ComponentModel.EventHandlerList>  
 [<span data-ttu-id="08426-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="08426-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="08426-114">Declarar eventos personalizados para evitar bloqueos</span><span class="sxs-lookup"><span data-stu-id="08426-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
