---
title: Operador Name
description: Aprenda a usar el operador Name en Visual Basic
ms.date: 10/27/2019
f1_keywords:
- NameOf
- vb.NameOf
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 0e72c4cb0c10113e53067ea4a743ca5ee77bcc95
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828908"
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

El `NameOf` operador está disponible en Visual Basic 14 y versiones posteriores.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](../index.md)
- [Operadores (Visual Basic)](index.md)
