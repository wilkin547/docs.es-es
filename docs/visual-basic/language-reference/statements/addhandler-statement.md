---
description: 'Más información sobre: AddHandler (instrucción)'
title: AddHandler (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c0c34abd7ff225765ab36278825a555e2b84b0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674108"
---
# <a name="addhandler-statement"></a><span data-ttu-id="2a682-103">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a682-103">AddHandler Statement</span></span>

<span data-ttu-id="2a682-104">Asocia un evento a un controlador de eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a682-104">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a682-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a682-105">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="2a682-106">Partes</span><span class="sxs-lookup"><span data-stu-id="2a682-106">Parts</span></span>  

|||
|---|---|
|<span data-ttu-id="2a682-107">event</span><span class="sxs-lookup"><span data-stu-id="2a682-107">event</span></span>|<span data-ttu-id="2a682-108">Nombre del evento que se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="2a682-108">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="2a682-109">Nombre de un procedimiento que controla el evento.</span><span class="sxs-lookup"><span data-stu-id="2a682-109">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="2a682-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a682-110">Remarks</span></span>  

 <span data-ttu-id="2a682-111">Las `AddHandler` `RemoveHandler` instrucciones y permiten iniciar y detener el control de eventos en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="2a682-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="2a682-112">La firma del `eventhandler` procedimiento debe coincidir con la firma del evento `event` .</span><span class="sxs-lookup"><span data-stu-id="2a682-112">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="2a682-113">La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="2a682-113">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="2a682-114">La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2a682-114">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="2a682-115">Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.</span><span class="sxs-lookup"><span data-stu-id="2a682-115">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="2a682-116">Para obtener más información, vea [identificadores](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="2a682-116">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a682-117">En el caso de los eventos personalizados, la `AddHandler` instrucción invoca al `AddHandler` descriptor de acceso del evento.</span><span class="sxs-lookup"><span data-stu-id="2a682-117">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="2a682-118">Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2a682-118">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a682-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a682-119">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="2a682-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a682-120">See also</span></span>

- [<span data-ttu-id="2a682-121">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a682-121">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="2a682-122">Asas</span><span class="sxs-lookup"><span data-stu-id="2a682-122">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="2a682-123">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a682-123">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="2a682-124">Eventos</span><span class="sxs-lookup"><span data-stu-id="2a682-124">Events</span></span>](../../programming-guide/language-features/events/index.md)
