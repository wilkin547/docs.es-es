---
title: "RemoveHandler (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82d130c6536df7d72977a028333293b4e0ee89de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="removehandler-statement"></a><span data-ttu-id="08a61-102">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="08a61-102">RemoveHandler Statement</span></span>
<span data-ttu-id="08a61-103">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="08a61-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08a61-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="08a61-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="08a61-105">Parts</span></span>  
  
|<span data-ttu-id="08a61-106">Término</span><span class="sxs-lookup"><span data-stu-id="08a61-106">Term</span></span>|<span data-ttu-id="08a61-107">Definición</span><span class="sxs-lookup"><span data-stu-id="08a61-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="08a61-108">El nombre del evento que se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="08a61-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="08a61-109">El nombre del procedimiento que controla actualmente el evento.</span><span class="sxs-lookup"><span data-stu-id="08a61-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08a61-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08a61-110">Remarks</span></span>  
 <span data-ttu-id="08a61-111">El `AddHandler` y `RemoveHandler` instrucciones permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="08a61-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08a61-112">Para los eventos personalizados, la `RemoveHandler` instrucción invoca el evento `RemoveHandler` descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="08a61-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="08a61-113">Para obtener más información sobre eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="08a61-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08a61-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="08a61-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="08a61-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="08a61-115">See Also</span></span>  
 [<span data-ttu-id="08a61-116">AddHandler (instrucción)</span><span class="sxs-lookup"><span data-stu-id="08a61-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="08a61-117">Handles</span><span class="sxs-lookup"><span data-stu-id="08a61-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="08a61-118">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="08a61-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="08a61-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="08a61-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
