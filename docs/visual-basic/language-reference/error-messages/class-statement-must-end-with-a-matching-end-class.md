---
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: d67f0e71dbdbf97420ec5b5ba4b6f06acfba1bd9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874611"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente

`Class` se usa para iniciar un `Class` bloque; por lo tanto, solo puede aparecer al principio del bloque, con una instrucción coincidente que `End Class` finaliza el bloque. O bien tiene una instrucción redundante `Class` o no ha finalizado el `Class` bloque con `End Class` .  
  
 **Identificador de error:** BC30481  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Busque y quite la instrucción `Class` innecesaria.  
  
- Concluye el `Class` bloque con una coincidencia `End Class` .  
  
## <a name="see-also"></a>Consulte también

- [End ( \<keyword> instrucción)](../statements/end-keyword-statement.md)
- [Instrucción Class](../statements/class-statement.md)
