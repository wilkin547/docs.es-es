---
title: El uso de una variable de iteración en una expresión lambda puede producir resultados inesperados.
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 7144a5fd4a197fddaf1ac4132df0ff70995ad067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594167"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>El uso de una variable de iteración en una expresión lambda puede producir resultados inesperados.
Uso de la variable de iteración en una expresión lambda puede producir resultados inesperados. En su lugar, cree una variable local dentro del bucle y asígnele el valor de la variable de iteración.  
  
 Esta advertencia aparece cuando se usa una variable de iteración de bucle en una expresión lambda que se declara dentro del bucle. Por ejemplo, en el ejemplo siguiente se hace que aparezca una advertencia.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 En el ejemplo siguiente se muestra que se pueden producir resultados inesperados.  
  
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
  
 El `For` bucle crea una matriz de expresiones lambda, cada una de las cuales devuelve el valor de la variable de iteración del bucle `i`. Cuando se evalúan las expresiones lambda en el `For Each` bucle, se podría espera ver 0, 1, 2, 3 y 4 muestra, los valores sucesivos de `i` en el `For` bucle. En su lugar, verá que el valor final de `i` muestra cinco veces:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42324  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asigne el valor de la variable de iteración a una variable local y use la variable local en la expresión lambda.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
