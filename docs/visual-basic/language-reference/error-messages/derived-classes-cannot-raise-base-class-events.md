---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 7b86420466d77a6aa45b1201a9375b4433e4b5ec
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163446"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="5988d-102">BC30029: las clases derivadas no pueden provocar eventos de clase base</span><span class="sxs-lookup"><span data-stu-id="5988d-102">BC30029: Derived classes cannot raise base class events</span></span>

<span data-ttu-id="5988d-103">Un evento solo se puede generar a partir del espacio de declaración en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="5988d-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="5988d-104">Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.</span><span class="sxs-lookup"><span data-stu-id="5988d-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>

 <span data-ttu-id="5988d-105">**Identificador de error:** BC30029</span><span class="sxs-lookup"><span data-stu-id="5988d-105">**Error ID:** BC30029</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5988d-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5988d-106">To correct this error</span></span>

- <span data-ttu-id="5988d-107">Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="5988d-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>

## <a name="see-also"></a><span data-ttu-id="5988d-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5988d-108">See also</span></span>

- [<span data-ttu-id="5988d-109">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5988d-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="5988d-110">RaiseEvent (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5988d-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
