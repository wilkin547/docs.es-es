---
description: 'Más información acerca de: BC30068: Expression es un valor y, por tanto, no puede ser el destino de una asignación.'
title: La expresión es un valor y, por lo tanto, no puede ser destino de una asignación
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 424ce9cb0183153454bc068e9da940948b737c47
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796371"
---
# <a name="bc30068-expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>BC30068: la expresión es un valor y, por tanto, no puede ser el destino de una asignación.

Una instrucción intenta asignar un valor a una expresión. Solo puede asignar un valor a una variable, propiedad o elemento de matriz de escritura en tiempo de ejecución. En el ejemplo siguiente se muestra cómo se puede producir este error.

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

Pueden aplicarse ejemplos similares a las propiedades y los elementos de la matriz.

**Acceso indirecto.** El acceso indirecto a través de un tipo de valor también puede generar este error. Considere el siguiente ejemplo de código, que intenta establecer el valor de accediendo <xref:System.Drawing.Point> indirectamente a través de <xref:System.Windows.Forms.Control.Location%2A> .

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

La última instrucción del ejemplo anterior produce un error porque solo crea una asignación temporal para la <xref:System.Drawing.Point> estructura devuelta por la <xref:System.Windows.Forms.Control.Location%2A> propiedad. Una estructura es un tipo de valor y la estructura temporal no se conserva después de que se ejecute la instrucción. El problema se resuelve declarando y usando una variable para <xref:System.Windows.Forms.Control.Location%2A> , lo que crea una asignación más permanente para la <xref:System.Drawing.Point> estructura. En el ejemplo siguiente se muestra código que puede reemplazar la última instrucción del ejemplo anterior.

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

**Identificador de error:** BC30068

## <a name="to-correct-this-error"></a>Para corregir este error

- Si la instrucción asigna un valor a una expresión, reemplace la expresión por una única variable, propiedad o elemento de matriz de escritura.

- Si la instrucción hace acceso indirecto a través de un tipo de valor (normalmente una estructura), cree una variable que contenga el tipo de valor.

- Asigne la estructura adecuada (u otro tipo de valor) a la variable.

- Use la variable para tener acceso a la propiedad y asignarle un valor.

## <a name="see-also"></a>Vea también

- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
- [Solución de problemas de procedimientos](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
