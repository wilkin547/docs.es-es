---
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 559595e9902ec2f0a19fd6b13e2c89fa1c2b52d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602417"
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
