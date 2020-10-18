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
# <a name="bc42324-using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="69800-102">BC42324: el uso de la variable de iteración en una expresión lambda puede tener resultados inesperados</span><span class="sxs-lookup"><span data-stu-id="69800-102">BC42324: Using the iteration variable in a lambda expression may have unexpected results</span></span>

<span data-ttu-id="69800-103">El uso de la variable de iteración en una expresión lambda puede tener resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="69800-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="69800-104">En su lugar, cree una variable local dentro del bucle y asígnele el valor de la variable de iteración.</span><span class="sxs-lookup"><span data-stu-id="69800-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>

 <span data-ttu-id="69800-105">Esta advertencia aparece cuando se usa una variable de iteración de bucle en una expresión lambda que se declara dentro del bucle.</span><span class="sxs-lookup"><span data-stu-id="69800-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="69800-106">Por ejemplo, el ejemplo siguiente hace que aparezca la advertencia.</span><span class="sxs-lookup"><span data-stu-id="69800-106">For example, the following example causes the warning to appear.</span></span>

```vb
For i As Integer = 1 To 10
    ' The warning is given for the use of i.
    Dim exampleFunc As Func(Of Integer) = Function() i
Next
```

 <span data-ttu-id="69800-107">En el ejemplo siguiente se muestran los resultados inesperados que se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="69800-107">The following example shows the unexpected results that might occur.</span></span>

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

 <span data-ttu-id="69800-108">El `For` bucle crea una matriz de expresiones lambda, cada una de las cuales devuelve el valor de la variable de iteración del bucle `i` .</span><span class="sxs-lookup"><span data-stu-id="69800-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="69800-109">Cuando se evalúan las expresiones lambda en el `For Each` bucle, podría esperar ver 0, 1, 2, 3 y 4, los valores sucesivos de `i` en el `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="69800-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="69800-110">En su lugar, verá el valor final de `i` mostrada cinco veces:</span><span class="sxs-lookup"><span data-stu-id="69800-110">Instead, you see the final value of `i` displayed five times:</span></span>

 `5`

 `5`

 `5`

 `5`

 `5`

 <span data-ttu-id="69800-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="69800-111">By default, this message is a warning.</span></span> <span data-ttu-id="69800-112">Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="69800-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="69800-113">**Identificador de error:** BC42324</span><span class="sxs-lookup"><span data-stu-id="69800-113">**Error ID:** BC42324</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="69800-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="69800-114">To correct this error</span></span>

- <span data-ttu-id="69800-115">Asigne el valor de la variable de iteración a una variable local y use la variable local en la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="69800-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="69800-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69800-116">See also</span></span>

- [<span data-ttu-id="69800-117">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="69800-117">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
