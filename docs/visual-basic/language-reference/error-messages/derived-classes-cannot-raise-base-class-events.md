---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 030c9c2ffa97572298b23f05c23e3af0df7387b0
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913159"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Las clases derivadas no pueden provocar eventos de clase base
Un evento puede generarse solo desde el espacio de declaración en el que se declara. Por lo tanto, una clase no puede provocar los eventos de cualquier otra clase, incluso uno desde el que se deriva.  
  
 **Identificador de error:** BC30029  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Mover el `Event` instrucción o el `RaiseEvent` instrucción para que estén en la misma clase.  
  
## <a name="see-also"></a>Vea también

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
