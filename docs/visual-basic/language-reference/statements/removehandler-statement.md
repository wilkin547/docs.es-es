---
title: Instrucción RemoveHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 47f35bd76d7734878e7b5b206b4aecd856276593
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582021"
---
# <a name="removehandler-statement"></a><span data-ttu-id="c7fb8-102">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="c7fb8-102">RemoveHandler Statement</span></span>
<span data-ttu-id="c7fb8-103">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c7fb8-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7fb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7fb8-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="c7fb8-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="c7fb8-105">Parts</span></span>  
  
|<span data-ttu-id="c7fb8-106">Término</span><span class="sxs-lookup"><span data-stu-id="c7fb8-106">Term</span></span>|<span data-ttu-id="c7fb8-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="c7fb8-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="c7fb8-108">Nombre del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="c7fb8-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="c7fb8-109">Nombre del procedimiento que está controlando el evento.</span><span class="sxs-lookup"><span data-stu-id="c7fb8-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7fb8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7fb8-110">Remarks</span></span>  
 <span data-ttu-id="c7fb8-111">Las instrucciones `AddHandler` y `RemoveHandler` permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="c7fb8-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7fb8-112">En el caso de los eventos personalizados, la instrucción `RemoveHandler` invoca al descriptor de acceso `RemoveHandler` del evento.</span><span class="sxs-lookup"><span data-stu-id="c7fb8-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="c7fb8-113">Para obtener más información sobre los eventos personalizados, vea [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c7fb8-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7fb8-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7fb8-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="c7fb8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7fb8-115">See also</span></span>

- [<span data-ttu-id="c7fb8-116">AddHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c7fb8-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="c7fb8-117">Handles</span><span class="sxs-lookup"><span data-stu-id="c7fb8-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="c7fb8-118">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c7fb8-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="c7fb8-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="c7fb8-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
