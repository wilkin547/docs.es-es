---
description: "Más información acerca de: BC30481: la instrucción ' Class ' debe terminar con la instrucción ' End Class ' correspondiente"
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: b0d2d89e9e3549b24f9c923e271b15b3b02026b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796786"
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
