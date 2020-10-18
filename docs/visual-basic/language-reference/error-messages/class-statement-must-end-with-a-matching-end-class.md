---
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 6889e97aad913f6911ce438892752542de0d10f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163199"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a>BC30481: la instrucción ' Class ' debe terminar con la instrucción ' End Class ' correspondiente

`Class` se usa para iniciar un `Class` bloque; por lo tanto, solo puede aparecer al principio del bloque, con una instrucción coincidente que `End Class` finaliza el bloque. O bien tiene una instrucción redundante `Class` o no ha finalizado el `Class` bloque con `End Class` .

 **Identificador de error:** BC30481

## <a name="to-correct-this-error"></a>Para corregir este error

- Busque y quite la instrucción `Class` innecesaria.

- Concluye el `Class` bloque con una coincidencia `End Class` .

## <a name="see-also"></a>Vea también

- [End ( \<keyword> instrucción)](../statements/end-keyword-statement.md)
- [Instrucción Class](../statements/class-statement.md)
