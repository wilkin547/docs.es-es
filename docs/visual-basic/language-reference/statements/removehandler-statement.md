---
title: RemoveHandler (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 8a9dc5874629c1687318496bd7c4016eb318c25a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831688"
---
# <a name="removehandler-statement"></a><span data-ttu-id="b29e1-102">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="b29e1-102">RemoveHandler Statement</span></span>
<span data-ttu-id="b29e1-103">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b29e1-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b29e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b29e1-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="b29e1-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="b29e1-105">Parts</span></span>  
  
|<span data-ttu-id="b29e1-106">Término</span><span class="sxs-lookup"><span data-stu-id="b29e1-106">Term</span></span>|<span data-ttu-id="b29e1-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="b29e1-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="b29e1-108">El nombre del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="b29e1-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="b29e1-109">El nombre del procedimiento que actualmente controla el evento.</span><span class="sxs-lookup"><span data-stu-id="b29e1-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b29e1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b29e1-110">Remarks</span></span>  
 <span data-ttu-id="b29e1-111">El `AddHandler` y `RemoveHandler` instrucciones le permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="b29e1-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b29e1-112">Para los eventos personalizados, el `RemoveHandler` instrucción invoca el evento `RemoveHandler` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="b29e1-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="b29e1-113">Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b29e1-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b29e1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b29e1-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="b29e1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b29e1-115">See also</span></span>

- [<span data-ttu-id="b29e1-116">AddHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b29e1-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="b29e1-117">Handles</span><span class="sxs-lookup"><span data-stu-id="b29e1-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="b29e1-118">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b29e1-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="b29e1-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="b29e1-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
