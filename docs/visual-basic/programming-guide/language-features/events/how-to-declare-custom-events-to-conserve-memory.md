---
title: 'Cómo: Declarar eventos personalizados para conservar memoria'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 3cc2d3ea57f1a8daf704c2c929baf3f2acf78c17
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345129"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="f9e1a-102">Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9e1a-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="f9e1a-103">Hay varias circunstancias en las que es importante que una aplicación mantenga bajo el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="f9e1a-104">Los eventos personalizados permiten que la aplicación use la memoria solo para los eventos que controla.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="f9e1a-105">De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo que almacena la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="f9e1a-106">Si una clase tiene muchos eventos sin usar, ocupan memoria innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="f9e1a-107">En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar eventos personalizados para administrar el uso de memoria con más detenimiento.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9e1a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9e1a-108">Example</span></span>  
 <span data-ttu-id="f9e1a-109">En este ejemplo, la clase utiliza una instancia de la clase <xref:System.ComponentModel.EventHandlerList>, almacenada en el campo `Events`, para almacenar información sobre los eventos en uso.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="f9e1a-110">La clase <xref:System.ComponentModel.EventHandlerList> es una clase de lista optimizada diseñada para contener delegados.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="f9e1a-111">Todos los eventos de la clase usan el campo `Events` para realizar un seguimiento de los métodos que controlan cada evento.</span><span class="sxs-lookup"><span data-stu-id="f9e1a-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="f9e1a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9e1a-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="f9e1a-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="f9e1a-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="f9e1a-114">Declarar eventos personalizados para evitar bloqueos</span><span class="sxs-lookup"><span data-stu-id="f9e1a-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
