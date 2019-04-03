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
ms.openlocfilehash: c016722332dafa3d3be91a1e9e98cc0ce9a49717
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835198"
---
# <a name="nested-control-structures-visual-basic"></a>Estructuras de control anidadas (Visual Basic)
Puede colocar las instrucciones de control dentro de otras instrucciones de control, por ejemplo un `If...Then...Else` bloquear dentro de un `For...Next` bucle. Una instrucción de control que se coloca dentro de otra instrucción de control se dice que *anidada*.  
  
## <a name="nesting-levels"></a>Niveles de anidamiento  
 Estructuras de control en Visual Basic se pueden anidar a tantos niveles como desee. Es una práctica común para facilitar la lectura de estructuras anidadas aplicar sangría al cuerpo de cada uno de ellos. El editor de desarrollo integrado (IDE) de entorno hace automáticamente.  
  
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
  
 En el ejemplo anterior, la primera `Next` instrucción cierra interno `For` bucle y la última `Next` instrucción cierra externo `For` bucle.  
  
 Del mismo modo, en anidados `If` instrucciones, el `End If` instrucciones se aplican automáticamente al más cercano antes `If` instrucción. Anidar `Do` bucles funcionan de manera similar, con la más interna `Loop` instrucción coincidencia interior `Do` instrucción.  
  
> [!NOTE]
>  Para muchas de las estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave en la estructura. Por ejemplo, al hacer clic en `If` en un `If...Then...Else` construcción, todas las instancias de `If`, `Then`, `ElseIf`, `Else`, y `End If` se resaltan en la construcción. Para mover a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>Anidar diferentes tipos de estructuras de Control  
 Puede anidar un tipo de estructura de control dentro de otro tipo. En el ejemplo siguiente se usa un `With` bloquear dentro de un `For Each` bucle y anidar `If` bloquea dentro de la `With` bloque.  
  
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
  
## <a name="overlapping-control-structures"></a>Estructuras de Control superpuestas  
 No se pueden superponer las estructuras de control. Esto significa que cualquier estructura anidada debe estar contenido completamente dentro de la siguiente estructura más interna. Por ejemplo, la organización siguiente no es válida porque la `For` bucle finaliza antes de interno `With` finaliza el bloque.  
  
 ![Diagrama que muestra un ejemplo de anidación no válida.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 El compilador de Visual Basic detecta estas estructuras de control que se superponen y señala un error de tiempo de compilación.  
  
## <a name="see-also"></a>Vea también

- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de decisión](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
