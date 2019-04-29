---
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 0619db618abd562bda86836bdd41bbcd6caee0f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649899"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
`Class` se usa para iniciar un `Class` bloquear; por lo tanto, solo puede aparecer al principio del bloque, con la instrucción correspondiente `End Class` final del bloque de instrucción. O bien hay un redundantes `Class` instrucción, o bien no ha terminado su `Class` bloque con `End Class`.  
  
 **Identificador de error:** BC30481  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Busque y quite la instrucción `Class` innecesaria.  
  
- Concluir la `Class` bloque con la instrucción correspondiente `End Class`.  
  
## <a name="see-also"></a>Vea también

- [End \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)
