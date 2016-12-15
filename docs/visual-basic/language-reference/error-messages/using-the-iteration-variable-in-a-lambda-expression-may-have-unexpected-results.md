---
title: "El uso de una variable de iteraci&#243;n en una expresi&#243;n lambda puede producir resultados inesperados. | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42324"
  - "bc42324"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42324"
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El uso de una variable de iteraci&#243;n en una expresi&#243;n lambda puede producir resultados inesperados.
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El uso de una variable de iteración en una expresión lambda puede producir resultados inesperados.En su lugar, cree una variable local dentro del bucle y asígnele el valor de la variable de iteración.  
  
 Esta advertencia aparece al utilizar una variable de iteración de bucle en una expresión lambda que se declara dentro del bucle.  El ejemplo siguiente provoca la aparición de la advertencia.  
  
```vb#  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 El ejemplo siguiente muestra los resultados inesperados que se pueden producir.  
  
```vb#  
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
  
 El bucle `For` crea una matriz de expresiones lambda, cada una de las cuales devuelve el valor de la variable de iteración del bucle `i`.  Cuando las expresiones lambda se evalúan en el bucle `For Each`, se espera ver 0, 1, 2, 3 y 4, los valores sucesivos de `i` en el bucle `For`.  En su lugar, ve el valor final de `i` mostrado cinco veces:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42324  
  
### Para corregir este error  
  
-   Asigne el valor de la variable de iteración a una variable local y use la variable local en la expresión lambda.  
  
    ```vb#  
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
  
## Vea también  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)