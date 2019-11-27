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
ms.openlocfilehash: 5818b13661fb4415c6f531b741b8a963a80bd2b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348150"
---
# <a name="nested-control-structures-visual-basic"></a>Estructuras de control anidadas (Visual Basic)
Puede colocar instrucciones de control dentro de otras instrucciones de control, por ejemplo, un bloque `If...Then...Else` dentro de un bucle `For...Next`. Una instrucción de control colocada dentro de otra instrucción de control se dice que está *anidada*.  
  
## <a name="nesting-levels"></a>Niveles de anidamiento  
 Las estructuras de control de Visual Basic se pueden anidar hasta tantos niveles como se desee. Es habitual que las estructuras anidadas sean más legibles mediante la sangría del cuerpo de cada una. El editor del entorno de desarrollo integrado (IDE) lo hace automáticamente.  
  
 En el ejemplo siguiente, el procedimiento `sumRows` agrega juntos los elementos positivos de cada fila de la matriz.  
  
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
  
 En el ejemplo anterior, la primera instrucción `Next` cierra el bucle de `For` interno y la última instrucción `Next` cierra el bucle de `For` externo.  
  
 Del mismo modo, en las instrucciones `If` anidadas, las instrucciones de `End If` se aplican automáticamente a la instrucción de `If` anterior más cercana. Los bucles `Do` anidados funcionan de manera similar, con la instrucción de `Loop` más interna que coincide con la instrucción de `Do` más interna.  
  
> [!NOTE]
> En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura. Por ejemplo, al hacer clic en `If` en una construcción de `If...Then...Else`, se resaltan todas las instancias de `If`, `Then`, `ElseIf`, `Else`y `End If` de la construcción. Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Anidar distintos tipos de estructuras de control  
 Puede anidar un tipo de estructura de control dentro de otro tipo. En el ejemplo siguiente se usa un bloque `With` dentro de un bucle de `For Each` y bloques de `If` anidados dentro del bloque de `With`.  
  
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
 No se pueden superponer estructuras de control. Esto significa que cualquier estructura anidada debe estar contenida completamente dentro de la siguiente estructura más interna. Por ejemplo, la siguiente disposición no es válida porque el bucle `For` finaliza antes de que finalice el bloque de `With` interno.  
  
 ![Diagrama que muestra un ejemplo de anidación no válida.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 El compilador Visual Basic detecta esas estructuras de control superpuestas y señala un error en tiempo de compilación.  
  
## <a name="see-also"></a>Vea también

- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
