---
title: Procedimiento Declarar eventos personalizados para conservar memoria (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: e4132f51f4dd85ad964042d05f7c5bc0a2e6e3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973165"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="1f885-102">Procedimiento Declarar eventos personalizados para conservar memoria (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f885-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="1f885-103">Hay varias circunstancias cuando es importante que una aplicación mantener el uso de memoria baja.</span><span class="sxs-lookup"><span data-stu-id="1f885-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="1f885-104">Eventos personalizados que la aplicación utilice solo para los eventos que controla la memoria.</span><span class="sxs-lookup"><span data-stu-id="1f885-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="1f885-105">De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo almacenar la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1f885-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="1f885-106">Si una clase tiene muchos eventos no usados, innecesariamente a tomar la memoria.</span><span class="sxs-lookup"><span data-stu-id="1f885-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="1f885-107">En lugar de usar la implementación predeterminada de los eventos que proporciona Visual Basic, puede usar los eventos personalizados para administrar el uso de memoria más detenidamente.</span><span class="sxs-lookup"><span data-stu-id="1f885-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f885-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f885-108">Example</span></span>  
 <span data-ttu-id="1f885-109">En este ejemplo, la clase utiliza una instancia de la <xref:System.ComponentModel.EventHandlerList> (clase), almacenado en el `Events` campo para almacenar información sobre los eventos en uso.</span><span class="sxs-lookup"><span data-stu-id="1f885-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="1f885-110">El <xref:System.ComponentModel.EventHandlerList> es una clase de lista optimizada están diseñada para contener los delegados.</span><span class="sxs-lookup"><span data-stu-id="1f885-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="1f885-111">Todos los eventos de la clase utilizan el `Events` campo para realizar un seguimiento de los métodos que controla cada evento.</span><span class="sxs-lookup"><span data-stu-id="1f885-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="1f885-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f885-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="1f885-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="1f885-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="1f885-114">Cómo: Declarar eventos personalizados para evitar el bloqueo</span><span class="sxs-lookup"><span data-stu-id="1f885-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
