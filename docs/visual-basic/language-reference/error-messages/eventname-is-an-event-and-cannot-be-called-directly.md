---
title: '&#39; &lt;eventname&gt;&#39; es un evento y no se puede llamar directamente'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="1edc6-102">&#39; &lt;eventname&gt;&#39; es un evento y no se puede llamar directamente</span><span class="sxs-lookup"><span data-stu-id="1edc6-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="1edc6-103">' <`eventname`>' es un evento y no se puede llamar directamente.</span><span class="sxs-lookup"><span data-stu-id="1edc6-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="1edc6-104">Use un `RaiseEvent` instrucción genera un evento.</span><span class="sxs-lookup"><span data-stu-id="1edc6-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="1edc6-105">Una llamada a procedimiento especifica un evento para el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1edc6-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="1edc6-106">Un controlador de eventos es un procedimiento, pero el propio evento es un dispositivo de señalización, que debe generarse y controlarse.</span><span class="sxs-lookup"><span data-stu-id="1edc6-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="1edc6-107">**Id. de error:** BC32022</span><span class="sxs-lookup"><span data-stu-id="1edc6-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1edc6-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1edc6-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="1edc6-109">Use un `RaiseEvent` instrucción para señalar un evento e invocar el procedimiento o procedimientos que lo controlan.</span><span class="sxs-lookup"><span data-stu-id="1edc6-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edc6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1edc6-110">See Also</span></span>  
 [<span data-ttu-id="1edc6-111">RaiseEvent (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1edc6-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
