---
title: Procedimiento Controlar el ámbito de una Variable (Visual Basic)
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
ms.openlocfilehash: 24a7ae3b8f3400beeaedb20ea6352ea44bdb7597
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794737"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Procedimiento Controlar el ámbito de una Variable (Visual Basic)
Normalmente, es una variable en *ámbito*, o visible como referencia, a lo largo de la región en la que se declara. En del algunos casos, la variable *nivel de acceso* puede influir en su ámbito.  
  
 Para obtener más información, consulta [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Ámbito en el nivel de procedimiento o bloque  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Para hacer visible solo dentro de un bloque de una variable  
  
- Colocar el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) para la variable entre el inicio y finalización de instrucciones de declaración de ese bloque, por ejemplo entre el `For` y `Next` las instrucciones de un `For` bucle.  
  
     Se puede hacer referencia a la variable solo desde dentro del bloque.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Para hacer que una variable sea visible solo dentro de un procedimiento  
  
- Colocar el `Dim` instrucción para la variable dentro del procedimiento pero fuera de cualquier bloque (como un `With`... `End With` bloque).  
  
     Se puede hacer referencia a la variable solo desde dentro del procedimiento, incluso dentro de cualquier bloque contenido en el procedimiento.  
  
## <a name="scope-at-module-or-namespace-level"></a>Ámbito en el nivel de módulo o Namespace  
 Para mayor comodidad, el término único *nivel de módulo* se aplica igualmente a los módulos, clases y estructuras. El nivel de acceso de una variable de nivel de módulo determina su ámbito. El espacio de nombres que contiene el módulo, clase o estructura también influye en el ámbito.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Para hacer visible a lo largo de un módulo, clase o estructura de una variable  
  
1. Colocar el `Dim` instrucción para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2. Incluir el [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave en el `Dim` instrucción.  
  
3. Puede hacer referencia a la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de él.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Para hacer visible a lo largo de un espacio de nombres de variable  
  
1. Colocar el `Dim` instrucción para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2. Incluir el [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [pública](../../../../visual-basic/language-reference/modifiers/public.md) palabra clave en el `Dim` instrucción.  
  
3. Puede hacer referencia a la variable desde cualquier lugar dentro del espacio de nombres que contiene el módulo, clase o estructura.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente declara una variable en el nivel de módulo y limita la visibilidad para el código dentro del módulo.  
  
```  
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
  
 En el ejemplo anterior, todos los procedimientos definen en el módulo `demonstrateScope` puede hacer referencia a la `String` variable `strMsg`. Cuando el `usePrivateVariable` se llama al procedimiento, se muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo.  
  
 La siguiente modificación en el ejemplo anterior, la variable de cadena `strMsg` puede hacer referencia a código en cualquier lugar en el espacio de nombres de su declaración.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Programación sólida  
 El ámbito más restringido el de una variable, menos posibilidades que tendrá de hacer referencia accidentalmente a ella en lugar de otra variable con el mismo nombre. También puede minimizar los problemas de comparación de referencias.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Más estrecha del ámbito de una variable, cuantos menos las posibilidades de que código malintencionado puede hacer incorrecto usar del mismo.  
  
## <a name="see-also"></a>Vea también

- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)
