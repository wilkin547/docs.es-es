---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0e9acf4b3e71295655c15ae9b1c80852c9aca8df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835146"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="05cb4-102">Las clases derivadas no pueden provocar eventos de clase base</span><span class="sxs-lookup"><span data-stu-id="05cb4-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="05cb4-103">Un evento puede generarse solo desde el espacio de declaración en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="05cb4-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="05cb4-104">Por lo tanto, una clase no puede provocar los eventos de cualquier otra clase, incluso uno desde el que se deriva.</span><span class="sxs-lookup"><span data-stu-id="05cb4-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="05cb4-105">**Identificador de error:** BC30029</span><span class="sxs-lookup"><span data-stu-id="05cb4-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="05cb4-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="05cb4-106">To correct this error</span></span>  
  
-   <span data-ttu-id="05cb4-107">Mover el `Event` instrucción o el `RaiseEvent` instrucción para que estén en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="05cb4-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05cb4-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="05cb4-108">See also</span></span>

- [<span data-ttu-id="05cb4-109">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="05cb4-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="05cb4-110">RaiseEvent (instrucción)</span><span class="sxs-lookup"><span data-stu-id="05cb4-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
