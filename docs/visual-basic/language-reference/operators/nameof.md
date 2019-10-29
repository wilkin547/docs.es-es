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
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="26bf5-103">Operador de nombre: Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26bf5-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="26bf5-104">El operador `NameOf` obtiene el nombre de una variable, un tipo o un miembro como la constante de cadena:</span><span class="sxs-lookup"><span data-stu-id="26bf5-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

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

<span data-ttu-id="26bf5-105">Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="26bf5-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="26bf5-106">El operador `NameOf` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="26bf5-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="26bf5-107">Puede usar el operador `NameOf` para hacer que el código de comprobación de argumentos sea más fácil de mantener:</span><span class="sxs-lookup"><span data-stu-id="26bf5-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

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

<span data-ttu-id="26bf5-108">El operador `NameOf` está disponible en Visual Basic 14 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="26bf5-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="26bf5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="26bf5-109">See also</span></span>

- [<span data-ttu-id="26bf5-110">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26bf5-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="26bf5-111">Operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26bf5-111">Operators (Visual Basic)</span></span>](index.md)
