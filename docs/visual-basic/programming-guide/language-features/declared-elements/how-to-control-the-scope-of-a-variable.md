---
title: Procedimiento para controlar el ámbito de una variable
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 8b21f22edea84448e3f2969c3e4b07c08a17a338
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357353"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Cómo: Controlar el ámbito de una variable (Visual Basic)
Normalmente, una variable está en el *ámbito*o es visible como referencia, en toda la región en la que se declara. En algunos casos, el nivel de *acceso* de la variable puede influir en su ámbito.  
  
 Para obtener más información, consulta [Scope in Visual Basic](scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Ámbito en el nivel de bloque o procedimiento  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Para hacer que una variable sea visible solo dentro de un bloque  
  
- Coloque la [instrucción Dim](../../../language-reference/statements/dim-statement.md) para la variable entre las instrucciones de declaración de inicio y finalización de ese bloque, por ejemplo, entre las `For` `Next` instrucciones y de un `For` bucle.  
  
     Solo puede hacer referencia a la variable desde dentro del bloque.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Para hacer que una variable sea visible solo dentro de un procedimiento  
  
- Coloque la `Dim` instrucción para la variable dentro del procedimiento pero fuera de cualquier bloque (como un `With` bloque... `End With` ).  
  
     Solo puede hacer referencia a la variable desde dentro del procedimiento, incluido dentro de cualquier bloque incluido en el procedimiento.  
  
## <a name="scope-at-module-or-namespace-level"></a>Ámbito en el nivel de módulo o espacio de nombres  
 Para mayor comodidad, el *nivel de módulo* de un solo término se aplica igualmente a los módulos, las clases y las estructuras. El nivel de acceso de una variable de nivel de módulo determina su ámbito. El espacio de nombres que contiene el módulo, la clase o la estructura también influye en el ámbito.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Para hacer que una variable sea visible en todo un módulo, clase o estructura  
  
1. Coloque la `Dim` instrucción para la variable dentro del módulo, la clase o la estructura, pero fuera de cualquier procedimiento.  
  
2. Incluya la palabra clave [Private](../../../language-reference/modifiers/private.md) en la `Dim` instrucción.  
  
3. Puede hacer referencia a la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de ella.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Para hacer que una variable sea visible en todo un espacio de nombres  
  
1. Coloque la `Dim` instrucción para la variable dentro del módulo, la clase o la estructura, pero fuera de cualquier procedimiento.  
  
2. Incluya la palabra clave [Friend](../../../language-reference/modifiers/friend.md) o [Public](../../../language-reference/modifiers/public.md) en la `Dim` instrucción.  
  
3. Puede hacer referencia a la variable desde cualquier lugar dentro del espacio de nombres que contiene el módulo, la clase o la estructura.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara una variable en el nivel de módulo y se limita su visibilidad al código dentro del módulo.  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 En el ejemplo anterior, todos los procedimientos definidos en Module `demonstrateScope` pueden hacer referencia a la `String` variable `strMsg` . Cuando `usePrivateVariable` se llama al procedimiento, se muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo.  
  
 Con la siguiente modificación en el ejemplo anterior, el código puede hacer referencia a la variable de cadena `strMsg` en cualquier lugar del espacio de nombres de su declaración.  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Programación sólida  
 Cuanto más estrecho sea el ámbito de una variable, menos oportunidades tendrá para hacer referencia accidentalmente a ella en lugar de a otra variable con el mismo nombre. También puede minimizar los problemas de coincidencia de referencias.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Cuanto más estrecho sea el ámbito de una variable, menor será la probabilidad de que el código malintencionado pueda hacer un uso inadecuado de ella.  
  
## <a name="see-also"></a>Consulte también

- [Ámbito en Visual Basic](scope.md)
- [Período de duración en Visual Basic](lifetime.md)
- [Niveles de acceso en Visual Basic](access-levels.md)
- [Variables](../variables/index.md)
- [Declaración de variable](../variables/variable-declaration.md)
- [Instrucción Dim](../../../language-reference/statements/dim-statement.md)
