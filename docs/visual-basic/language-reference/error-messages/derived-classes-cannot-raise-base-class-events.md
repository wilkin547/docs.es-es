---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: c59212a28ba27123a7db9163ff7437c159a3d310
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409704"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="6f984-102">Las clases derivadas no pueden provocar eventos de clase base</span><span class="sxs-lookup"><span data-stu-id="6f984-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="6f984-103">Un evento solo se puede generar a partir del espacio de declaración en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="6f984-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="6f984-104">Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.</span><span class="sxs-lookup"><span data-stu-id="6f984-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="6f984-105">**Identificador de error:** BC30029</span><span class="sxs-lookup"><span data-stu-id="6f984-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f984-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6f984-106">To correct this error</span></span>  
  
- <span data-ttu-id="6f984-107">Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="6f984-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f984-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f984-108">See also</span></span>

- [<span data-ttu-id="6f984-109">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="6f984-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="6f984-110">RaiseEvent (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="6f984-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
