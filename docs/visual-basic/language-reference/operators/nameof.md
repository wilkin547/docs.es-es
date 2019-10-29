---
title: 'Operador de nombre: Visual Basic'
description: Aprenda a usar el operador Name en Visual Basic
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 8416bb1a1715c1c37b62cac6a9e0b427a9c72547
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041356"
---
# <a name="nameof-operator---visual-basic"></a>Operador de nombre: Visual Basic

El operador `NameOf` obtiene el nombre de una variable, un tipo o un miembro como la constante de cadena:

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

El operador `NameOf` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.

Puede usar el operador `NameOf` para hacer que el código de comprobación de argumentos sea más fácil de mantener:

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

El operador `NameOf` está disponible en Visual Basic 14 y versiones posteriores.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](../index.md)
- [Operadores (Visual Basic)](index.md)
