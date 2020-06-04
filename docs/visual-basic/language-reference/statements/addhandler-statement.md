---
title: AddHandler (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408489"
---
# <a name="addhandler-statement"></a><span data-ttu-id="ddefd-102">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="ddefd-102">AddHandler Statement</span></span>
<span data-ttu-id="ddefd-103">Asocia un evento a un controlador de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ddefd-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddefd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddefd-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="ddefd-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ddefd-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="ddefd-106">event</span><span class="sxs-lookup"><span data-stu-id="ddefd-106">event</span></span>|<span data-ttu-id="ddefd-107">Nombre del evento que se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="ddefd-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="ddefd-108">Nombre de un procedimiento que controla el evento.</span><span class="sxs-lookup"><span data-stu-id="ddefd-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="ddefd-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ddefd-109">Remarks</span></span>  
 <span data-ttu-id="ddefd-110">Las `AddHandler` `RemoveHandler` instrucciones y permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="ddefd-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="ddefd-111">La firma del `eventhandler` procedimiento debe coincidir con la firma del evento `event` .</span><span class="sxs-lookup"><span data-stu-id="ddefd-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="ddefd-112">La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="ddefd-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="ddefd-113">La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ddefd-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="ddefd-114">Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.</span><span class="sxs-lookup"><span data-stu-id="ddefd-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="ddefd-115">Para obtener más información, vea [identificadores](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ddefd-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ddefd-116">En el caso de los eventos personalizados, la `AddHandler` instrucción invoca al `AddHandler` descriptor de acceso del evento.</span><span class="sxs-lookup"><span data-stu-id="ddefd-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="ddefd-117">Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ddefd-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddefd-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddefd-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="ddefd-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddefd-119">See also</span></span>

- [<span data-ttu-id="ddefd-120">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="ddefd-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="ddefd-121">Asas</span><span class="sxs-lookup"><span data-stu-id="ddefd-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="ddefd-122">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="ddefd-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="ddefd-123">Eventos</span><span class="sxs-lookup"><span data-stu-id="ddefd-123">Events</span></span>](../../programming-guide/language-features/events/index.md)
