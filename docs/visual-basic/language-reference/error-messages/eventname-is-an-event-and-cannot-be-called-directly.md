---
title: "'<eventname>' es un evento y no se le puede llamar directamente"
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803330"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="f0493-102">'\<eventname >' es un evento y no se puede llamar directamente</span><span class="sxs-lookup"><span data-stu-id="f0493-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="f0493-103">' <`eventname`>' es un evento y no se puede llamar directamente.</span><span class="sxs-lookup"><span data-stu-id="f0493-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="f0493-104">Use un `RaiseEvent` instrucción para generar un evento.</span><span class="sxs-lookup"><span data-stu-id="f0493-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="f0493-105">Una llamada a procedimiento especifica un evento para el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f0493-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="f0493-106">Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que debe generarse y controlarse.</span><span class="sxs-lookup"><span data-stu-id="f0493-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="f0493-107">**Identificador de error:** BC32022</span><span class="sxs-lookup"><span data-stu-id="f0493-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0493-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f0493-108">To correct this error</span></span>  
  
1. <span data-ttu-id="f0493-109">Use un `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o procedimientos que lo procesan.</span><span class="sxs-lookup"><span data-stu-id="f0493-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0493-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0493-110">See also</span></span>

- [<span data-ttu-id="f0493-111">RaiseEvent (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f0493-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
