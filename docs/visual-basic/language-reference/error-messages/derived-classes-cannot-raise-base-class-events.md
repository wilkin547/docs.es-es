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
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a>BC30029: las clases derivadas no pueden provocar eventos de clase base

Un evento solo se puede generar a partir del espacio de declaración en el que se declara. Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.

 **Identificador de error:** BC30029

## <a name="to-correct-this-error"></a>Para corregir este error

- Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.

## <a name="see-also"></a>Vea también

- [Event (Instrucción)](../statements/event-statement.md)
- [RaiseEvent (Instrucción)](../statements/raiseevent-statement.md)
