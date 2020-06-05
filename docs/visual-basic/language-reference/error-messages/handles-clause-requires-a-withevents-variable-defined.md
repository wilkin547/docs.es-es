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
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>La cláusula Handles requiere una variable WithEvents definida en el tipo contenedor o en uno de sus tipos base

No proporcionó una `WithEvents` variable en la `Handles` cláusula. La `Handles` palabra clave al final de una declaración de procedimiento hace que controle los eventos generados por una variable de objeto declarada mediante la `WithEvents` palabra clave.

**Identificador de error:** BC30506

## <a name="to-correct-this-error"></a>Para corregir este error

Proporcione la `WithEvents` variable necesaria.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, Visual Basic genera un error del compilador `BC30506` porque la palabra clave [WithEvents](../modifiers/withevents.md) no se utiliza en la definición de la <xref:System.Timers.Timer?displayProperty=nameWithType> instancia.

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

En el ejemplo siguiente se compila correctamente porque la `_timer1` variable se define con la `WithEvents` palabra clave:

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

## <a name="see-also"></a>Consulte también

- [Asas](../statements/handles-clause.md)
