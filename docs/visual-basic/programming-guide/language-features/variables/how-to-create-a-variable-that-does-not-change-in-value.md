---
title: Procedimiento Crear una Variable que no cambia de valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 3a9fa93b69c9abb42b2dd7eae623048f3628999e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663572"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Procedimiento Crear una Variable que no cambia de valor (Visual Basic)
La noción de una variable que no cambia su valor podría parecer contradictorios. Pero existen situaciones en una constante no es factible y resulta útil disponer de una variable con un valor fijo. En este caso puede definir una variable miembro con el [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) palabra clave.  
  
 No puede usar el [instrucción Const](../../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante en las siguientes circunstancias:  
  
- El `Const` instrucción no acepta el tipo de datos que desea usar  
  
- Se desconoce el valor en tiempo de compilación  
  
- No puede calcular el valor constante en tiempo de compilación  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Para crear una variable que no cambia de valor  
  
1. En el nivel de módulo, declare una variable miembro con el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)e incluyen el [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) palabra clave.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     Puede especificar `ReadOnly` solo en una variable de miembro. Esto significa que debe definir la variable en el nivel de módulo, fuera de cualquier procedimiento.  
  
2. Si se puede calcular el valor en una única instrucción en tiempo de compilación, utilice una cláusula de inicialización en el `Dim` instrucción. Siga el [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula con un signo igual (`=`), seguido de una expresión. Asegúrese de que el compilador puede evaluar esta expresión en un valor constante.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Puede asignar un valor a un `ReadOnly` variable sólo una vez. Una vez hecho esto, ningún código nunca puede cambiar su valor.  
  
     Si no conoce el valor en tiempo de compilación, o no se puede calcular en tiempo de compilación en una sola instrucción, se puede asignar en tiempo de ejecución en un constructor. Para ello, debe declarar la `ReadOnly` variable en el nivel de clase o estructura. En el constructor para esa clase o estructura, calcular el valor fijo de la variable y asigne a la variable antes de devolver desde el constructor.  
  
## <a name="see-also"></a>Vea también

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)
