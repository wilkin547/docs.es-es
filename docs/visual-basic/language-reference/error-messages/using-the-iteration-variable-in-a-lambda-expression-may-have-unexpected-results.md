---
title: El uso de una variable de iteración en una expresión lambda puede producir resultados inesperados.
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: d0deea94084565ea91debe2b6db30def4cd9e00e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161496"
---
# <a name="bc42324-using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>BC42324: el uso de la variable de iteración en una expresión lambda puede tener resultados inesperados

El uso de la variable de iteración en una expresión lambda puede tener resultados inesperados. En su lugar, cree una variable local dentro del bucle y asígnele el valor de la variable de iteración.

 Esta advertencia aparece cuando se usa una variable de iteración de bucle en una expresión lambda que se declara dentro del bucle. Por ejemplo, el ejemplo siguiente hace que aparezca la advertencia.

```vb
For i As Integer = 1 To 10
    ' The warning is given for the use of i.
    Dim exampleFunc As Func(Of Integer) = Function() i
Next
```

 En el ejemplo siguiente se muestran los resultados inesperados que se pueden producir.

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            array1(i) = Function() i
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

 El `For` bucle crea una matriz de expresiones lambda, cada una de las cuales devuelve el valor de la variable de iteración del bucle `i` . Cuando se evalúan las expresiones lambda en el `For Each` bucle, podría esperar ver 0, 1, 2, 3 y 4, los valores sucesivos de `i` en el `For` bucle. En su lugar, verá el valor final de `i` mostrada cinco veces:

 `5`

 `5`

 `5`

 `5`

 `5`

 De forma predeterminada, este mensaje es una advertencia. Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC42324

## <a name="to-correct-this-error"></a>Para corregir este error

- Asigne el valor de la variable de iteración a una variable local y use la variable local en la expresión lambda.

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            Dim j = i
            array1(i) = Function() j
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

## <a name="see-also"></a>Consulte también

- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
