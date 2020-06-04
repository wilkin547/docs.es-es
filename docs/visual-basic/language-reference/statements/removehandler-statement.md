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
ms.openlocfilehash: 3514a79f2430b148e6a3727b83029b4e207a677b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404257"
---
# <a name="removehandler-statement"></a><span data-ttu-id="0bb25-102">RemoveHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="0bb25-102">RemoveHandler Statement</span></span>
<span data-ttu-id="0bb25-103">Quita la asociación entre un evento y un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0bb25-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bb25-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="0bb25-105">Partes</span><span class="sxs-lookup"><span data-stu-id="0bb25-105">Parts</span></span>  
  
|<span data-ttu-id="0bb25-106">Término</span><span class="sxs-lookup"><span data-stu-id="0bb25-106">Term</span></span>|<span data-ttu-id="0bb25-107">Definición</span><span class="sxs-lookup"><span data-stu-id="0bb25-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="0bb25-108">Nombre del evento que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="0bb25-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="0bb25-109">Nombre del procedimiento que está controlando el evento.</span><span class="sxs-lookup"><span data-stu-id="0bb25-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bb25-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0bb25-110">Remarks</span></span>  
 <span data-ttu-id="0bb25-111">Las `AddHandler` `RemoveHandler` instrucciones y permiten iniciar y detener el control de eventos para un evento concreto en cualquier momento durante la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="0bb25-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0bb25-112">En el caso de los eventos personalizados, la `RemoveHandler` instrucción invoca al `RemoveHandler` descriptor de acceso del evento.</span><span class="sxs-lookup"><span data-stu-id="0bb25-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="0bb25-113">Para obtener más información sobre los eventos personalizados, vea [Event Statement](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0bb25-113">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bb25-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0bb25-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="0bb25-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bb25-115">See also</span></span>

- [<span data-ttu-id="0bb25-116">AddHandler (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="0bb25-116">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="0bb25-117">Asas</span><span class="sxs-lookup"><span data-stu-id="0bb25-117">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="0bb25-118">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="0bb25-118">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="0bb25-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="0bb25-119">Events</span></span>](../../programming-guide/language-features/events/index.md)
