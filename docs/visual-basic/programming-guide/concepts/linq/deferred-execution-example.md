---
title: Ejemplo de ejecución diferida
ms.date: 07/20/2015
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
ms.openlocfilehash: 863b018b6047d61f6fb4a5c1ac68151ed69d24a1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410804"
---
# <a name="deferred-execution-example-visual-basic"></a><span data-ttu-id="7eeaf-102">Ejemplo de ejecución aplazada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eeaf-102">Deferred Execution Example (Visual Basic)</span></span>

<span data-ttu-id="7eeaf-103">En este tema se muestra cómo la ejecución aplazada y la evaluación diferid afectan a la ejecución de las consultas de LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="7eeaf-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>

## <a name="example"></a><span data-ttu-id="7eeaf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7eeaf-104">Example</span></span>

<span data-ttu-id="7eeaf-105">El siguiente ejemplo muestra el orden de ejecución cuando se usa un método de extensión que utiliza la ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="7eeaf-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="7eeaf-106">El ejemplo declara una matriz de tres cadenas.</span><span class="sxs-lookup"><span data-stu-id="7eeaf-106">The example declares an array of three strings.</span></span> <span data-ttu-id="7eeaf-107">A continuación recorre en iteración la recopilación devuelta por `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="7eeaf-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module Module1

    <Extension()>
    Private Iterator Function ConvertCollectionToUpperCase(
    ByVal source As IEnumerable(Of String)) _
    As IEnumerable(Of String)
        For Each str As String In source
            Console.WriteLine("ToUpper: source {0}", str)
            Yield str.ToUpper()
        Next
    End Function

    Sub Main()
        Dim stringArray = New String() {"abc", "def", "ghi"}

        Dim q = From str In stringArray.ConvertCollectionToUpperCase()
                Select str

        For Each Str As String In q
            Console.WriteLine("Main: str {0}", Str)
        Next
    End Sub

End Module
```

<span data-ttu-id="7eeaf-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7eeaf-108">This example produces the following output:</span></span>

```console
ToUpper: source abc
Main: str ABC
ToUpper: source def
Main: str DEF
ToUpper: source ghi
Main: str GHI
```

<span data-ttu-id="7eeaf-109">Tenga en cuenta que durante el recorrido en iteración de la recopilación devuelta por `ConvertCollectionToUpperCase`, cada elemento se recupera de la matriz de cadenas de origen y se convierte a mayúsculas antes de que se recupere el siguiente elemento de la matriz de cadenas de origen.</span><span class="sxs-lookup"><span data-stu-id="7eeaf-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>

<span data-ttu-id="7eeaf-110">Puede ver que no se convierte a mayúsculas toda la matriz de cadenas antes de que se procese cada elemento en el bucle `foreach` de `Main`.</span><span class="sxs-lookup"><span data-stu-id="7eeaf-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7eeaf-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7eeaf-111">See also</span></span>

- [<span data-ttu-id="7eeaf-112">Tutorial: ejecución aplazada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eeaf-112">Tutorial: Deferred Execution (Visual Basic)</span></span>](tutorial-deferred-execution.md)
