---
title: "Uso de la variable de iteración en una expresión lambda puede tener resultados inesperados | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
dev_langs:
- VB
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5b293ec344d816e40d369757fa4d11710b7ecd8d
ms.lasthandoff: 03/13/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>El uso de una variable de iteración en una expresión lambda puede producir resultados inesperados.
Es posible que usar la variable de iteración en una expresión lambda tenga resultados inesperados. En su lugar, cree una variable local dentro del bucle y asígnele el valor de la variable de iteración.  
  
 Esta advertencia aparece cuando se utiliza una variable de iteración de bucle en una expresión lambda que se declara dentro del bucle. Por ejemplo, en el ejemplo siguiente se genera la advertencia que aparezcan.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 El ejemplo siguiente muestra los resultados inesperados que pueden producirse.  
  
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
  
 El `For` bucle crea una matriz de expresiones lambda, cada una de las cuales devuelve el valor de la variable de iteración del bucle `i`. Cuando se evalúan las expresiones lambda en el `For Each` el bucle, se espera ver 0, 1, 2, 3 y 4 muestra, los valores sucesivos de `i` en el `For` bucle. En su lugar, verá que el valor final de `i` mostrado cinco veces:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información acerca de cómo ocultar las advertencias o tratar las advertencias como errores, vea [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
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
