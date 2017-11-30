---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords: BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70dde8b96980adfd618e38b9ce142cdec56a6b13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="fa10a-102">Las clases derivadas no pueden provocar eventos de clase base</span><span class="sxs-lookup"><span data-stu-id="fa10a-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="fa10a-103">Un evento se puede generar solo desde el espacio de declaración en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="fa10a-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="fa10a-104">Por lo tanto, una clase no puede provocar los eventos de cualquier otra clase, incluso uno del que se deriva.</span><span class="sxs-lookup"><span data-stu-id="fa10a-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="fa10a-105">**Id. de error:** BC30029</span><span class="sxs-lookup"><span data-stu-id="fa10a-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa10a-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="fa10a-106">To correct this error</span></span>  
  
-   <span data-ttu-id="fa10a-107">Mover el `Event` instrucción o `RaiseEvent` instrucción para que estén en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="fa10a-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa10a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa10a-108">See Also</span></span>  
 [<span data-ttu-id="fa10a-109">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fa10a-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="fa10a-110">RaiseEvent (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fa10a-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
