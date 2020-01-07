---
title: Operador Name
description: Aprenda a usar el operador Name en Visual Basic
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: e7dd55bfd98b34449b9f1a35375198598f57b46f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347018"
---
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="38a87-103">Operador de nombre: Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38a87-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="38a87-104">El operador `NameOf` obtiene el nombre de una variable, un tipo o un miembro como la constante de cadena:</span><span class="sxs-lookup"><span data-stu-id="38a87-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

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

<span data-ttu-id="38a87-105">Como se muestra en el ejemplo anterior, en el caso de un tipo y un espacio de nombres, el nombre generado por lo general no está [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span><span class="sxs-lookup"><span data-stu-id="38a87-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="38a87-106">El operador `NameOf` se evalúa en tiempo de compilación y no tiene efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="38a87-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="38a87-107">Puede usar el operador `NameOf` para hacer que el código de comprobación de argumentos sea más fácil de mantener:</span><span class="sxs-lookup"><span data-stu-id="38a87-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

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

<span data-ttu-id="38a87-108">El operador `NameOf` está disponible en Visual Basic 14 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="38a87-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="38a87-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="38a87-109">See also</span></span>

- [<span data-ttu-id="38a87-110">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38a87-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="38a87-111">Operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38a87-111">Operators (Visual Basic)</span></span>](index.md)
