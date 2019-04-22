---
title: AddHandler (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 1e8d8f512f163d82f074a5ad53fbb38a10904dfa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827086"
---
# <a name="addhandler-statement"></a><span data-ttu-id="79e17-102">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="79e17-102">AddHandler Statement</span></span>
<span data-ttu-id="79e17-103">Asocia un evento a un controlador de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="79e17-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79e17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79e17-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="79e17-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="79e17-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="79e17-106">evento</span><span class="sxs-lookup"><span data-stu-id="79e17-106">event</span></span>|<span data-ttu-id="79e17-107">El nombre del evento para controlar.</span><span class="sxs-lookup"><span data-stu-id="79e17-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="79e17-108">El nombre de un procedimiento que controla el evento.</span><span class="sxs-lookup"><span data-stu-id="79e17-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="79e17-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79e17-109">Remarks</span></span>  
 <span data-ttu-id="79e17-110">El `AddHandler` y `RemoveHandler` instrucciones le permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="79e17-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="79e17-111">La firma de la `eventhandler` procedimiento debe coincidir con la firma del evento `event`.</span><span class="sxs-lookup"><span data-stu-id="79e17-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="79e17-112">La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="79e17-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="79e17-113">La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="79e17-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="79e17-114">Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.</span><span class="sxs-lookup"><span data-stu-id="79e17-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="79e17-115">Para obtener más información, consulte [controla](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="79e17-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79e17-116">Para los eventos personalizados, el `AddHandler` instrucción invoca el evento `AddHandler` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="79e17-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="79e17-117">Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="79e17-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="79e17-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79e17-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="79e17-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="79e17-119">See also</span></span>

- [<span data-ttu-id="79e17-120">RemoveHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="79e17-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="79e17-121">Handles</span><span class="sxs-lookup"><span data-stu-id="79e17-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="79e17-122">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="79e17-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="79e17-123">Eventos</span><span class="sxs-lookup"><span data-stu-id="79e17-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
