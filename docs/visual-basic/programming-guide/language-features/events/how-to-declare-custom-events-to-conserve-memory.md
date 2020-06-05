---
title: Procedimiento para declarar eventos personalizados para conservar memoria
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: c9a049d3f15d5620152f064888a97bd0be5d46b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405136"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="7dc30-102">Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dc30-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="7dc30-103">Hay varias circunstancias en las que es importante que una aplicación mantenga bajo el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="7dc30-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="7dc30-104">Los eventos personalizados permiten que la aplicación use la memoria solo para los eventos que controla.</span><span class="sxs-lookup"><span data-stu-id="7dc30-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="7dc30-105">De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo que almacena la información del evento.</span><span class="sxs-lookup"><span data-stu-id="7dc30-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="7dc30-106">Si una clase tiene muchos eventos sin usar, ocupan memoria innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="7dc30-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="7dc30-107">En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar eventos personalizados para administrar el uso de memoria con más detenimiento.</span><span class="sxs-lookup"><span data-stu-id="7dc30-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dc30-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7dc30-108">Example</span></span>  
 <span data-ttu-id="7dc30-109">En este ejemplo, la clase utiliza una instancia de la <xref:System.ComponentModel.EventHandlerList> clase, almacenada en el `Events` campo, para almacenar información sobre los eventos en uso.</span><span class="sxs-lookup"><span data-stu-id="7dc30-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="7dc30-110">La <xref:System.ComponentModel.EventHandlerList> clase es una clase de lista optimizada diseñada para contener delegados.</span><span class="sxs-lookup"><span data-stu-id="7dc30-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="7dc30-111">Todos los eventos de la clase usan el `Events` campo para realizar un seguimiento de los métodos que controlan cada evento.</span><span class="sxs-lookup"><span data-stu-id="7dc30-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="7dc30-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dc30-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="7dc30-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="7dc30-113">Events</span></span>](index.md)
- [<span data-ttu-id="7dc30-114">Procedimiento para declarar eventos personalizados para evitar bloqueos</span><span class="sxs-lookup"><span data-stu-id="7dc30-114">How to: Declare Custom Events To Avoid Blocking</span></span>](how-to-declare-custom-events-to-avoid-blocking.md)
