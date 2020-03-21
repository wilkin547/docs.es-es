---
title: Estructuras de control anidadas
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266929"
---
# <a name="nested-control-structures-visual-basic"></a>Estructuras de control anidadas (Visual Basic)
Puede colocar instrucciones de control dentro de otras `If...Then...Else` instrucciones `For...Next` de control, por ejemplo, un bloque dentro de un bucle. Se dice que una instrucción de control colocada dentro de otra instrucción de control está *anidada.*  
  
## <a name="nesting-levels"></a>Niveles de anidación  
 Las estructuras de control de Visual Basic se pueden anidar en tantos niveles como desee. Es una práctica común hacer que las estructuras anidadas sean más legibles mediante la sangría del cuerpo de cada una. El editor de entorno de desarrollo integrado (IDE) lo hace automáticamente.  
  
 En el ejemplo siguiente, el procedimiento `sumRows` suma los elementos positivos de cada fila de la matriz.  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 En el ejemplo anterior, `Next` la primera `For` instrucción cierra `Next` el bucle `For` interno y la última instrucción cierra el bucle externo.  
  
 Del mismo modo, en las instrucciones anidadas, `If` las `End If` instrucciones se aplican automáticamente a la instrucción anterior `If` más cercana. Los `Do` bucles anidados funcionan de forma `Loop` similar, con `Do` la instrucción más interna que coincide con la instrucción más interna.  
  
> [!NOTE]
> Para muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura. Por ejemplo, al `If` hacer `If...Then...Else` clic en una `If` `Then`construcción, se resaltan todas las instancias de , , `ElseIf` `Else`, y `End If` en la construcción. Para pasar a la palabra clave resaltada siguiente o anterior, presione CTRL+MAYO+FLECHA ABAJO o CTRL+MAYO+FLECHA ARRIBA.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Anidar diferentes tipos de estructuras de control  
 Puede anidar un tipo de estructura de control dentro de otro tipo. En el ejemplo `With` siguiente `For Each` se utiliza `If` un `With` bloque dentro de un bucle y bloques anidados dentro del bloque.  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>Estructuras de control superpuestas  
 No se pueden superponer estructuras de control. Esto significa que cualquier estructura anidada debe estar completamente contenida dentro de la siguiente estructura más interna. Por ejemplo, la siguiente disposición no es válida porque el `For` bucle finaliza antes de que finalice el bloque interno. `With`  
  
 ![Diagrama que muestra un ejemplo de anidamiento no válido.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 El compilador de Visual Basic detecta estas estructuras de control superpuestas y señala un error en tiempo de compilación.  
  
## <a name="see-also"></a>Consulte también

- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
