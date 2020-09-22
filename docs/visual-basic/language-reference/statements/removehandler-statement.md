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
ms.openlocfilehash: a815241f20be12b3b7b4f2b87d50a8965021bbf0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871943"
---
# <a name="removehandler-statement"></a><span data-ttu-id="e31bd-102">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="e31bd-102">RemoveHandler Statement</span></span>

<span data-ttu-id="e31bd-103">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="e31bd-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e31bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e31bd-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="e31bd-105">Partes</span><span class="sxs-lookup"><span data-stu-id="e31bd-105">Parts</span></span>  
  
|<span data-ttu-id="e31bd-106">Término</span><span class="sxs-lookup"><span data-stu-id="e31bd-106">Term</span></span>|<span data-ttu-id="e31bd-107">Definición</span><span class="sxs-lookup"><span data-stu-id="e31bd-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="e31bd-108">Nombre del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="e31bd-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="e31bd-109">Nombre del procedimiento que está controlando el evento.</span><span class="sxs-lookup"><span data-stu-id="e31bd-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e31bd-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e31bd-110">Remarks</span></span>  

 <span data-ttu-id="e31bd-111">Las `AddHandler` `RemoveHandler` instrucciones y permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="e31bd-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e31bd-112">En el caso de los eventos personalizados, la `RemoveHandler` instrucción invoca al `RemoveHandler` descriptor de acceso del evento.</span><span class="sxs-lookup"><span data-stu-id="e31bd-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="e31bd-113">Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e31bd-113">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e31bd-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e31bd-114">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="e31bd-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e31bd-115">See also</span></span>

- [<span data-ttu-id="e31bd-116">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="e31bd-116">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="e31bd-117">Asas</span><span class="sxs-lookup"><span data-stu-id="e31bd-117">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="e31bd-118">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="e31bd-118">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="e31bd-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="e31bd-119">Events</span></span>](../../programming-guide/language-features/events/index.md)
