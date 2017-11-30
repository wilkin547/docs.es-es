---
title: "Cómo: Controlar el ámbito de una variable (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7284d344e3bf0fdd0f900f2a820d6c8db4a4bf74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Cómo: Controlar el ámbito de una variable (Visual Basic)
Normalmente, una variable consiste en *ámbito*, o como referencia, en toda la región en la que se declara está visible. En del algunos casos, la variable *nivel de acceso* puede influir en su ámbito.  
  
 Para obtener más información, consulte [ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Ámbito en el nivel de procedimiento o bloque  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Para hacer visible solo dentro de un bloque de una variable  
  
-   Lugar la [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) para la variable entre el inicio y finalización de instrucciones de declaración de dicho bloque, por ejemplo entre el `For` y `Next` las instrucciones de un `For` bucle.  
  
     Puede hacer referencia a la variable únicamente desde dentro del bloque.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Para hacer que una variable sea visible sólo dentro de un procedimiento  
  
-   Lugar la `Dim` instrucción para la variable dentro del procedimiento pero fuera de cualquier bloque (como un `With`... `End With` bloque).  
  
     Puede hacer referencia a la variable únicamente desde dentro del procedimiento, incluso dentro de cualquier bloque contenido en el procedimiento.  
  
## <a name="scope-at-module-or-namespace-level"></a>Ámbito en el nivel de módulo o Namespace  
 Para mayor comodidad, el término único *nivel de módulo* se aplica por igual a módulos, clases y estructuras. El nivel de acceso de una variable de nivel de módulo determina su ámbito. El espacio de nombres que contiene el módulo, clase o estructura también influye en el ámbito.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Para hacer que una variable sea visible a lo largo de un módulo, clase o estructura  
  
1.  Lugar el `Dim` instrucción para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2.  Incluir el [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave en el `Dim` instrucción.  
  
3.  Puede hacer referencia a la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de él.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Para hacer que una variable sea visible a lo largo de un espacio de nombres  
  
1.  Lugar el `Dim` instrucción para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2.  Incluir el [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [público](../../../../visual-basic/language-reference/modifiers/public.md) palabra clave en el `Dim` instrucción.  
  
3.  Puede hacer referencia a la variable desde cualquier lugar dentro del espacio de nombres que contiene el módulo, clase o estructura.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara una variable en el nivel de módulo y se limita su visibilidad al código dentro del módulo.  
  
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
  
 En el ejemplo anterior, todos los procedimientos definen en el módulo `demonstrateScope` pueden hacer referencia a la `String` variable `strMsg`. Cuando el `usePrivateVariable` se llama al procedimiento, se muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo.  
  
 Con la modificación siguiente al ejemplo anterior, la variable de cadena `strMsg` puede hacer referencia a código en cualquier lugar en el espacio de nombres de su declaración.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Programación sólida  
 El ámbito más restringido el de una variable, menos posibilidades que tendrá de hacer referencia accidentalmente a ella en lugar de otra variable con el mismo nombre. También puede minimizar los problemas de concordancia de referencias.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Más se limita el ámbito de una variable, cuanto más pequeño las posibilidades de que un código malintencionado puede hacer incorrecto usar del mismo.  
  
## <a name="see-also"></a>Vea también  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)
