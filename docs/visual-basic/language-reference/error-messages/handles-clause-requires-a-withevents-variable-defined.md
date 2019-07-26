---
title: La cláusula Handles requiere una variable WithEvents definida en el tipo contenedor o en uno de sus tipos base
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 04c94d3d32660d1a186a9bb377c49a53e1451be6
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512734"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="041d5-102">La cláusula Handles requiere una variable WithEvents definida en el tipo contenedor o en uno de sus tipos base</span><span class="sxs-lookup"><span data-stu-id="041d5-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>
<span data-ttu-id="041d5-103">No proporcionó una `WithEvents` variable en la `Handles` cláusula.</span><span class="sxs-lookup"><span data-stu-id="041d5-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="041d5-104">La `Handles` palabra clave al final de una declaración de procedimiento hace que controle los eventos generados por una variable de `WithEvents` objeto declarada mediante la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="041d5-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>
  
 <span data-ttu-id="041d5-105">**IDENTIFICADOR de error:** BC30506</span><span class="sxs-lookup"><span data-stu-id="041d5-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="041d5-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="041d5-106">To correct this error</span></span>
  
- <span data-ttu-id="041d5-107">Proporcione la variable `WithEvents` necesaria.</span><span class="sxs-lookup"><span data-stu-id="041d5-107">Supply the necessary `WithEvents` variable.</span></span>
  
## <a name="example"></a><span data-ttu-id="041d5-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="041d5-108">Example</span></span>

<span data-ttu-id="041d5-109">En el ejemplo siguiente, Visual Basic genera un error `BC30506` del compilador porque la palabra clave [WithEvents](../modifiers/withevents.md) no se utiliza <xref:System.Timers.Timer?displayProperty=nameWithType> en la definición de la instancia.</span><span class="sxs-lookup"><span data-stu-id="041d5-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="041d5-110">En el ejemplo siguiente se compila correctamente porque la `_timer1` variable se define con la `WithEvents` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="041d5-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="041d5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="041d5-111">See also</span></span>

- [<span data-ttu-id="041d5-112">Handles</span><span class="sxs-lookup"><span data-stu-id="041d5-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
