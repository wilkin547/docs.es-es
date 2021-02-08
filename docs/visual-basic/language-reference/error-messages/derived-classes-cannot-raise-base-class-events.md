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
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a>BC30029: las clases derivadas no pueden provocar eventos de clase base

Un evento solo se puede generar a partir del espacio de declaración en el que se declara. Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.

 **Identificador de error:** BC30029

## <a name="to-correct-this-error"></a>Para corregir este error

- Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.

## <a name="see-also"></a>Vea también

- [Event (Instrucción)](../statements/event-statement.md)
- [RaiseEvent (Instrucción)](../statements/raiseevent-statement.md)
