---
title: Estructuras de control anidadas (Visual Basic)
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
ms.openlocfilehash: f559bf603605873f1b9155e9a96cb367e5420343
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941683"
---
# <a name="nested-control-structures-visual-basic"></a>Estructuras de control anidadas (Visual Basic)
Puede colocar instrucciones de control dentro de otras instrucciones de control, por `If...Then...Else` ejemplo, un `For...Next` bloque dentro de un bucle. Una instrucción de control colocada dentro de otra instrucción decontrol se dice que está anidada.  
  
## <a name="nesting-levels"></a>Niveles de anidamiento  
 Las estructuras de control de Visual Basic se pueden anidar hasta tantos niveles como se desee. Es habitual que las estructuras anidadas sean más legibles mediante la sangría del cuerpo de cada una. El editor del entorno de desarrollo integrado (IDE) lo hace automáticamente.  
  
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
  
 En el ejemplo anterior, la primera `Next` instrucción cierra el bucle interno `For` y la última `Next` instrucción cierra el bucle externo `For` .  
  
 Del mismo modo, en `If` las instrucciones anidadas, las `End If` instrucciones se aplican `If` automáticamente a la instrucción anterior más cercana. Los bucles anidados funcionan de manera similar, con la instrucción `Loop` más interna que coincide con la instrucción más interna. `Do` `Do`  
  
> [!NOTE]
> En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura. Por ejemplo, al hacer clic `If` en en `If...Then...Else` una construcción, se resaltan `ElseIf`todas `Else`las instancias `End If` de `If`, `Then`,, y en la construcción. Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Anidar distintos tipos de estructuras de control  
 Puede anidar un tipo de estructura de control dentro de otro tipo. En el ejemplo siguiente se `With` usa un bloque `For Each` dentro de un bucle `If` y bloques anidados dentro del `With` bloque.  
  
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
 No se pueden superponer estructuras de control. Esto significa que cualquier estructura anidada debe estar contenida completamente dentro de la siguiente estructura más interna. Por ejemplo, la siguiente disposición no es válida porque `For` el bucle finaliza antes de que `With` finalice el bloque interno.  
  
 ![Diagrama que muestra un ejemplo de anidación no válida.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 El compilador Visual Basic detecta esas estructuras de control superpuestas y señala un error en tiempo de compilación.  
  
## <a name="see-also"></a>Vea también

- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
