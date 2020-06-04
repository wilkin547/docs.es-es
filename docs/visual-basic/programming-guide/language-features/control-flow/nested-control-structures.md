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
ms.openlocfilehash: 539ad639320615c1e53176fe47e5468864aa21d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414394"
---
# <a name="nested-control-structures-visual-basic"></a>Estructuras de control anidadas (Visual Basic)
Puede colocar instrucciones de control dentro de otras instrucciones de control, por ejemplo, un `If...Then...Else` bloque dentro de un `For...Next` bucle. Una instrucción de control colocada dentro de otra instrucción de control se dice que está *anidada*.  
  
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
  
 En el ejemplo anterior, la primera `Next` instrucción cierra el bucle interno `For` y la última `Next` instrucción cierra el `For` bucle externo.  
  
 Del mismo modo, en `If` las instrucciones anidadas, las `End If` instrucciones se aplican automáticamente a la instrucción anterior más cercana `If` . `Do`Los bucles anidados funcionan de manera similar, con la instrucción más interna `Loop` que coincide con la instrucción más interna `Do` .  
  
> [!NOTE]
> En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura. Por ejemplo, al hacer clic `If` en en una `If...Then...Else` construcción, `If` se resaltan todas las instancias de,,, `Then` `ElseIf` `Else` y `End If` en la construcción. Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Anidar distintos tipos de estructuras de control  
 Puede anidar un tipo de estructura de control dentro de otro tipo. En el ejemplo siguiente se usa un `With` bloque dentro de un `For Each` bucle y bloques anidados `If` dentro del `With` bloque.  
  
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
 No se pueden superponer estructuras de control. Esto significa que cualquier estructura anidada debe estar contenida completamente dentro de la siguiente estructura más interna. Por ejemplo, la siguiente disposición no es válida porque el `For` bucle finaliza antes de que `With` finalice el bloque interno.  
  
 ![Diagrama que muestra un ejemplo de anidación no válida.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 El compilador Visual Basic detecta esas estructuras de control superpuestas y señala un error en tiempo de compilación.  
  
## <a name="see-also"></a>Consulte también

- [Flujo de control](index.md)
- [Estructuras de decisión](decision-structures.md)
- [Estructuras de bucle](loop-structures.md)
- [Estructuras de control adicionales](other-control-structures.md)
