---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 365ce6ece1d964d3fac2a44f7ed4c1e16f44c95d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586404"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Las clases derivadas no pueden provocar eventos de clase base
Un evento se puede generar solo desde el espacio de declaración en el que se declara. Por lo tanto, una clase no puede provocar los eventos de cualquier otra clase, incluso uno del que se deriva.  
  
 **Id. de error:** BC30029  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Mover el `Event` instrucción o `RaiseEvent` instrucción para que estén en la misma clase.  
  
## <a name="see-also"></a>Vea también  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
