---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874482"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="b881c-102">Las clases derivadas no pueden provocar eventos de clase base</span><span class="sxs-lookup"><span data-stu-id="b881c-102">Derived classes cannot raise base class events</span></span>

<span data-ttu-id="b881c-103">Un evento solo se puede generar a partir del espacio de declaración en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="b881c-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="b881c-104">Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.</span><span class="sxs-lookup"><span data-stu-id="b881c-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="b881c-105">**Identificador de error:** BC30029</span><span class="sxs-lookup"><span data-stu-id="b881c-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b881c-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b881c-106">To correct this error</span></span>  
  
- <span data-ttu-id="b881c-107">Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="b881c-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b881c-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b881c-108">See also</span></span>

- [<span data-ttu-id="b881c-109">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="b881c-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="b881c-110">RaiseEvent (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="b881c-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
