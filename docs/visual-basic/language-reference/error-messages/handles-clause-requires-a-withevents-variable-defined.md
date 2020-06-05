---
title: La cláusula Handles requiere una variable WithEvents definida en el tipo contenedor o en uno de sus tipos base
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 94c4229d4036382e344cffb09295e218642c55d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402906"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="add96-102">La cláusula Handles requiere una variable WithEvents definida en el tipo contenedor o en uno de sus tipos base</span><span class="sxs-lookup"><span data-stu-id="add96-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="add96-103">No proporcionó una `WithEvents` variable en la `Handles` cláusula.</span><span class="sxs-lookup"><span data-stu-id="add96-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="add96-104">La `Handles` palabra clave al final de una declaración de procedimiento hace que controle los eventos generados por una variable de objeto declarada mediante la `WithEvents` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="add96-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="add96-105">**Identificador de error:** BC30506</span><span class="sxs-lookup"><span data-stu-id="add96-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="add96-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="add96-106">To correct this error</span></span>

<span data-ttu-id="add96-107">Proporcione la `WithEvents` variable necesaria.</span><span class="sxs-lookup"><span data-stu-id="add96-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="add96-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="add96-108">Example</span></span>

<span data-ttu-id="add96-109">En el ejemplo siguiente, Visual Basic genera un error del compilador `BC30506` porque la palabra clave [WithEvents](../modifiers/withevents.md) no se utiliza en la definición de la <xref:System.Timers.Timer?displayProperty=nameWithType> instancia.</span><span class="sxs-lookup"><span data-stu-id="add96-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

<span data-ttu-id="add96-110">En el ejemplo siguiente se compila correctamente porque la `_timer1` variable se define con la `WithEvents` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="add96-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a><span data-ttu-id="add96-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="add96-111">See also</span></span>

- [<span data-ttu-id="add96-112">Asas</span><span class="sxs-lookup"><span data-stu-id="add96-112">Handles</span></span>](../statements/handles-clause.md)
