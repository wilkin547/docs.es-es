---
title: "El uso de una variable de iteración en una expresión lambda puede producir resultados inesperados."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords: BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb707cd4e09a149d21b70bb0f998a40c7ed58b49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="52613-102">El uso de una variable de iteración en una expresión lambda puede producir resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="52613-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="52613-103">Uso de la variable de iteración en una expresión lambda puede producir resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="52613-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="52613-104">En su lugar, cree una variable local dentro del bucle y asígnele el valor de la variable de iteración.</span><span class="sxs-lookup"><span data-stu-id="52613-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="52613-105">Esta advertencia aparece cuando se usa una variable de iteración de bucle en una expresión lambda que se declara dentro del bucle.</span><span class="sxs-lookup"><span data-stu-id="52613-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="52613-106">Por ejemplo, en el ejemplo siguiente se hace que aparezca una advertencia.</span><span class="sxs-lookup"><span data-stu-id="52613-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="52613-107">En el ejemplo siguiente se muestra que se pueden producir resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="52613-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="52613-108">El `For` bucle crea una matriz de expresiones lambda, cada una de las cuales devuelve el valor de la variable de iteración del bucle `i`.</span><span class="sxs-lookup"><span data-stu-id="52613-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="52613-109">Cuando se evalúan las expresiones lambda en el `For Each` bucle, se podría espera ver 0, 1, 2, 3 y 4 muestra, los valores sucesivos de `i` en el `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="52613-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="52613-110">En su lugar, verá que el valor final de `i` muestra cinco veces:</span><span class="sxs-lookup"><span data-stu-id="52613-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="52613-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="52613-111">By default, this message is a warning.</span></span> <span data-ttu-id="52613-112">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="52613-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="52613-113">**Id. de error:** BC42324</span><span class="sxs-lookup"><span data-stu-id="52613-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="52613-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="52613-114">To correct this error</span></span>  
  
-   <span data-ttu-id="52613-115">Asigne el valor de la variable de iteración a una variable local y use la variable local en la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="52613-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="52613-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="52613-116">See Also</span></span>  
 [<span data-ttu-id="52613-117">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="52613-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
