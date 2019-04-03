---
title: "'<eventname>' es un evento y no se le puede llamar directamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: eb0b40a80d37788bcab32791d7ed701a77505371
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831449"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="e2003-102">'\<eventname >' es un evento y no se puede llamar directamente</span><span class="sxs-lookup"><span data-stu-id="e2003-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="e2003-103">' <`eventname`>' es un evento y no se puede llamar directamente.</span><span class="sxs-lookup"><span data-stu-id="e2003-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="e2003-104">Use un `RaiseEvent` instrucción para generar un evento.</span><span class="sxs-lookup"><span data-stu-id="e2003-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="e2003-105">Una llamada a procedimiento especifica un evento para el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e2003-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="e2003-106">Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que debe generarse y controlarse.</span><span class="sxs-lookup"><span data-stu-id="e2003-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="e2003-107">**Identificador de error:** BC32022</span><span class="sxs-lookup"><span data-stu-id="e2003-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e2003-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e2003-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="e2003-109">Use un `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o procedimientos que lo procesan.</span><span class="sxs-lookup"><span data-stu-id="e2003-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2003-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2003-110">See also</span></span>

- [<span data-ttu-id="e2003-111">RaiseEvent (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e2003-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
