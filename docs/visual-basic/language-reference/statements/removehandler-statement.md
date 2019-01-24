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
ms.openlocfilehash: 27cdd2753507c6fc4d5c5041607e2ccb425b81b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560625"
---
# <a name="removehandler-statement"></a><span data-ttu-id="5aee9-102">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5aee9-102">RemoveHandler Statement</span></span>
<span data-ttu-id="5aee9-103">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5aee9-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aee9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5aee9-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="5aee9-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5aee9-105">Parts</span></span>  
  
|<span data-ttu-id="5aee9-106">Término</span><span class="sxs-lookup"><span data-stu-id="5aee9-106">Term</span></span>|<span data-ttu-id="5aee9-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="5aee9-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="5aee9-108">El nombre del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="5aee9-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="5aee9-109">El nombre del procedimiento que actualmente controla el evento.</span><span class="sxs-lookup"><span data-stu-id="5aee9-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5aee9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5aee9-110">Remarks</span></span>  
 <span data-ttu-id="5aee9-111">El `AddHandler` y `RemoveHandler` instrucciones le permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="5aee9-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5aee9-112">Para los eventos personalizados, el `RemoveHandler` instrucción invoca el evento `RemoveHandler` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="5aee9-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="5aee9-113">Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5aee9-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aee9-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5aee9-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5aee9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5aee9-115">See also</span></span>
- [<span data-ttu-id="5aee9-116">AddHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5aee9-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="5aee9-117">Handles</span><span class="sxs-lookup"><span data-stu-id="5aee9-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="5aee9-118">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5aee9-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="5aee9-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="5aee9-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
