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
# <a name="derived-classes-cannot-raise-base-class-events"></a>Las clases derivadas no pueden provocar eventos de clase base

Un evento solo se puede generar a partir del espacio de declaración en el que se declara. Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.  
  
 **Identificador de error:** BC30029  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.  
  
## <a name="see-also"></a>Consulte también

- [Event (Instrucción)](../statements/event-statement.md)
- [RaiseEvent (Instrucción)](../statements/raiseevent-statement.md)
