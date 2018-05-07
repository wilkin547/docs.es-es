---
title: 'Cómo: Crear una variable que no cambia de valor (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d63c254abe6d12c094e0d1252c9721f668947f09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Cómo: Crear una variable que no cambia de valor (Visual Basic)
La noción de una variable que no cambia su valor podría parecer contradictoria. Pero hay ocasiones una constante no es factible y resulta útil disponer de una variable con un valor fijo. En tal caso puede definir una variable miembro con la [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) palabra clave.  
  
 No se puede utilizar el [instrucción Const](../../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante en las circunstancias siguientes:  
  
-   El `Const` instrucción no acepta el tipo de datos que desea usar  
  
-   No se conoce el valor en tiempo de compilación  
  
-   No puede calcular el valor constante en tiempo de compilación  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Para crear una variable que no cambia de valor  
  
1.  En el nivel de módulo, declare una variable de miembro con el [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)e incluyen el [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) palabra clave.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     Puede especificar `ReadOnly` solo en una variable de miembro. Esto significa que debe definir la variable en el nivel de módulo, fuera de cualquier procedimiento.  
  
2.  Si puede calcular el valor en una única instrucción en tiempo de compilación, use una cláusula de inicialización en el `Dim` instrucción. Siga el [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula con un signo igual (`=`), seguido de una expresión. Asegúrese de que el compilador puede evaluar esta expresión en un valor constante.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Puede asignar un valor a un `ReadOnly` variable sólo una vez. Una vez hecho esto, ningún código puede cambiar alguna vez a su valor.  
  
     Si no conoce el valor en tiempo de compilación, o lo que no se puede calcular en tiempo de compilación en una sola instrucción, se puede asignar en tiempo de ejecución en un constructor. Para ello, debe declarar la `ReadOnly` variable en el nivel de clase o estructura. En el constructor para esa clase o estructura, valor fijo de la variable de proceso y asignarlo a la variable antes de devolver desde el constructor.  
  
## <a name="see-also"></a>Vea también  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)
