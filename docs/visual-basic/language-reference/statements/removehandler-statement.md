---
title: RemoveHandler (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333035"
---
# <a name="removehandler-statement"></a><span data-ttu-id="3f5aa-102">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3f5aa-102">RemoveHandler Statement</span></span>
<span data-ttu-id="3f5aa-103">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="3f5aa-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f5aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f5aa-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="3f5aa-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="3f5aa-105">Parts</span></span>  
  
|<span data-ttu-id="3f5aa-106">Término</span><span class="sxs-lookup"><span data-stu-id="3f5aa-106">Term</span></span>|<span data-ttu-id="3f5aa-107">Definición</span><span class="sxs-lookup"><span data-stu-id="3f5aa-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="3f5aa-108">Nombre del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="3f5aa-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="3f5aa-109">Nombre del procedimiento que está controlando el evento.</span><span class="sxs-lookup"><span data-stu-id="3f5aa-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f5aa-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f5aa-110">Remarks</span></span>  
 <span data-ttu-id="3f5aa-111">Las instrucciones `AddHandler` y `RemoveHandler` permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="3f5aa-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f5aa-112">En el caso de los eventos personalizados, la instrucción `RemoveHandler` invoca al descriptor de acceso `RemoveHandler` del evento.</span><span class="sxs-lookup"><span data-stu-id="3f5aa-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="3f5aa-113">Para obtener más información sobre los eventos personalizados, vea [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3f5aa-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f5aa-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f5aa-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="3f5aa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f5aa-115">See also</span></span>

- [<span data-ttu-id="3f5aa-116">AddHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3f5aa-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="3f5aa-117">Handles</span><span class="sxs-lookup"><span data-stu-id="3f5aa-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="3f5aa-118">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3f5aa-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="3f5aa-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="3f5aa-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
