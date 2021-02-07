---
description: 'Más información sobre: RemoveHandler (instrucción)'
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
ms.openlocfilehash: 699db9edfc029b4149246e8b654645040ae6d89e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741307"
---
# <a name="removehandler-statement"></a><span data-ttu-id="35107-103">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="35107-103">RemoveHandler Statement</span></span>

<span data-ttu-id="35107-104">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="35107-104">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35107-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35107-105">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="35107-106">Partes</span><span class="sxs-lookup"><span data-stu-id="35107-106">Parts</span></span>  
  
|<span data-ttu-id="35107-107">Término</span><span class="sxs-lookup"><span data-stu-id="35107-107">Term</span></span>|<span data-ttu-id="35107-108">Definición</span><span class="sxs-lookup"><span data-stu-id="35107-108">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="35107-109">Nombre del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="35107-109">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="35107-110">Nombre del procedimiento que está controlando el evento.</span><span class="sxs-lookup"><span data-stu-id="35107-110">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35107-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35107-111">Remarks</span></span>  

 <span data-ttu-id="35107-112">Las `AddHandler` `RemoveHandler` instrucciones y permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="35107-112">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35107-113">En el caso de los eventos personalizados, la `RemoveHandler` instrucción invoca al `RemoveHandler` descriptor de acceso del evento.</span><span class="sxs-lookup"><span data-stu-id="35107-113">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="35107-114">Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="35107-114">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="35107-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35107-115">Example</span></span>  

 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="35107-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="35107-116">See also</span></span>

- [<span data-ttu-id="35107-117">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="35107-117">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="35107-118">Asas</span><span class="sxs-lookup"><span data-stu-id="35107-118">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="35107-119">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="35107-119">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="35107-120">Eventos</span><span class="sxs-lookup"><span data-stu-id="35107-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
