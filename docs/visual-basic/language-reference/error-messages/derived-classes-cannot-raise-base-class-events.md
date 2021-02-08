---
description: 'Más información sobre: BC30029: las clases derivadas no pueden provocar eventos de clase base'
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 68546f2654f7c34fcb309d5af68e237d5f1eac79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796605"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="975dc-103">BC30029: las clases derivadas no pueden provocar eventos de clase base</span><span class="sxs-lookup"><span data-stu-id="975dc-103">BC30029: Derived classes cannot raise base class events</span></span>

<span data-ttu-id="975dc-104">Un evento solo se puede generar a partir del espacio de declaración en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="975dc-104">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="975dc-105">Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.</span><span class="sxs-lookup"><span data-stu-id="975dc-105">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>

 <span data-ttu-id="975dc-106">**Identificador de error:** BC30029</span><span class="sxs-lookup"><span data-stu-id="975dc-106">**Error ID:** BC30029</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="975dc-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="975dc-107">To correct this error</span></span>

- <span data-ttu-id="975dc-108">Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="975dc-108">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>

## <a name="see-also"></a><span data-ttu-id="975dc-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="975dc-109">See also</span></span>

- [<span data-ttu-id="975dc-110">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="975dc-110">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="975dc-111">RaiseEvent (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="975dc-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
