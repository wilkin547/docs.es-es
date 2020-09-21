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
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="3e81b-103">Operador de nombre: Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3e81b-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="3e81b-104">El operador `NameOf` obtiene el nombre de una variable, un tipo o un miembro como la constante de cadena:</span><span class="sxs-lookup"><span data-stu-id="3e81b-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

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

<span data-ttu-id="3e81b-105">Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="3e81b-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="3e81b-106">El operador `NameOf` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3e81b-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="3e81b-107">Puede usar el operador `NameOf` para hacer que el código de comprobación de argumentos sea más fácil de mantener:</span><span class="sxs-lookup"><span data-stu-id="3e81b-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

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

<span data-ttu-id="3e81b-108">El `NameOf` operador está disponible en Visual Basic 14 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3e81b-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e81b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e81b-109">See also</span></span>

- [<span data-ttu-id="3e81b-110">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3e81b-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="3e81b-111">Operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e81b-111">Operators (Visual Basic)</span></span>](index.md)
