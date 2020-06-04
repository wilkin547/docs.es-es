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
# <a name="derived-classes-cannot-raise-base-class-events"></a>Las clases derivadas no pueden provocar eventos de clase base
Un evento solo se puede generar a partir del espacio de declaración en el que se declara. Por lo tanto, una clase no puede generar eventos de cualquier otra clase, incluso una de la que se deriva.  
  
 **Identificador de error:** BC30029  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Mueva la `Event` instrucción o la `RaiseEvent` instrucción para que estén en la misma clase.  
  
## <a name="see-also"></a>Consulte también

- [Event (Instrucción)](../statements/event-statement.md)
- [RaiseEvent (Instrucción)](../statements/raiseevent-statement.md)
