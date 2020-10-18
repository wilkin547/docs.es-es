---
title: La cláusula Handles requiere una variable WithEvents definida en el tipo contenedor o en uno de sus tipos base
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: e16a157d0621d5baecb06ce118e3ab390bf68cf8
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162887"
---
# <a name="bc30506-handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="1f45d-102">BC30506: la cláusula handles requiere una variable WithEvents definida en el tipo contenedor o en uno de sus tipos base</span><span class="sxs-lookup"><span data-stu-id="1f45d-102">BC30506: Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="1f45d-103">No proporcionó una `WithEvents` variable en la `Handles` cláusula.</span><span class="sxs-lookup"><span data-stu-id="1f45d-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="1f45d-104">La `Handles` palabra clave al final de una declaración de procedimiento hace que controle los eventos generados por una variable de objeto declarada mediante la `WithEvents` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1f45d-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="1f45d-105">**Identificador de error:** BC30506</span><span class="sxs-lookup"><span data-stu-id="1f45d-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1f45d-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1f45d-106">To correct this error</span></span>

<span data-ttu-id="1f45d-107">Proporcione la `WithEvents` variable necesaria.</span><span class="sxs-lookup"><span data-stu-id="1f45d-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="1f45d-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f45d-108">Example</span></span>

<span data-ttu-id="1f45d-109">En el ejemplo siguiente, Visual Basic genera un error del compilador `BC30506` porque la palabra clave [WithEvents](../modifiers/withevents.md) no se utiliza en la definición de la <xref:System.Timers.Timer?displayProperty=nameWithType> instancia.</span><span class="sxs-lookup"><span data-stu-id="1f45d-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="1f45d-110">En el ejemplo siguiente se compila correctamente porque la `_timer1` variable se define con la `WithEvents` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="1f45d-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1f45d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f45d-111">See also</span></span>

- [<span data-ttu-id="1f45d-112">Asas</span><span class="sxs-lookup"><span data-stu-id="1f45d-112">Handles</span></span>](../statements/handles-clause.md)
