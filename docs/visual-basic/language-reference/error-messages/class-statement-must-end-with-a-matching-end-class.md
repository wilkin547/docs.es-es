---
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 01c231f577d21028e9ef92f37c7ac5f7f1fe2aa3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415393"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
`Class`se usa para iniciar un `Class` bloque; por lo tanto, solo puede aparecer al principio del bloque, con una instrucción coincidente que `End Class` finaliza el bloque. O bien tiene una instrucción redundante `Class` o no ha finalizado el `Class` bloque con `End Class` .  
  
 **Identificador de error:** BC30481  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Busque y quite la instrucción `Class` innecesaria.  
  
- Concluye el `Class` bloque con una coincidencia `End Class` .  
  
## <a name="see-also"></a>Consulte también

- [End ( \<keyword> instrucción)](../statements/end-keyword-statement.md)
- [Instrucción Class](../statements/class-statement.md)
