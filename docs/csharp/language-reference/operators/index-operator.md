---
title: 'Operador []: Referencia de C#'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835595"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c8899-102">Operador [] (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c8899-102">[] operator (C# Reference)</span></span>

<span data-ttu-id="c8899-103">Los corchetes, `[]`, se suelen usar para el acceso a matriz, indizador o elemento de puntero.</span><span class="sxs-lookup"><span data-stu-id="c8899-103">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

<span data-ttu-id="c8899-104">Para obtener más información sobre el acceso a elemento de puntero, consulte [Cómo: Obtener acceso a un elemento de matriz con un puntero](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="c8899-104">For more information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="c8899-105">También usa los corchetes para especificar [atributos](../../programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="c8899-105">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a><span data-ttu-id="c8899-106">Acceso a matriz</span><span class="sxs-lookup"><span data-stu-id="c8899-106">Array access</span></span>

<span data-ttu-id="c8899-107">En el ejemplo siguiente se muestra cómo se obtiene acceso a los elementos de matriz:</span><span class="sxs-lookup"><span data-stu-id="c8899-107">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

<span data-ttu-id="c8899-108">Si un índice de matriz se encuentra fuera de los límites de la dimensión correspondiente de una matriz, se produce una excepción <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="c8899-108">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="c8899-109">Tal como se muestra en el ejemplo anterior, también usa corchetes en declaración de un tipo de matriz y la creación de instancias de matriz.</span><span class="sxs-lookup"><span data-stu-id="c8899-109">As the preceding example shows, you also use square brackets in declaration of an array type and instantiation of array instances.</span></span>

<span data-ttu-id="c8899-110">Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="c8899-110">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="indexer-access"></a><span data-ttu-id="c8899-111">Acceso a indizador</span><span class="sxs-lookup"><span data-stu-id="c8899-111">Indexer access</span></span>

<span data-ttu-id="c8899-112">En el siguiente ejemplo se usa el tipo <xref:System.Collections.Generic.Dictionary%602> de .NET para mostrar el acceso a indizador:</span><span class="sxs-lookup"><span data-stu-id="c8899-112">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

<span data-ttu-id="c8899-113">Los indizadores le permiten indizar las instancias de un tipo definido por el usuario de un modo similar a la indización de matrices.</span><span class="sxs-lookup"><span data-stu-id="c8899-113">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="c8899-114">A diferencia de los índices de matriz, que deben ser enteros, los argumentos de indizador se pueden declarar para ser de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="c8899-114">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="c8899-115">Para más información sobre los indizadores, consulte [Indizadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c8899-115">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c8899-116">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="c8899-116">Operator overloadability</span></span>

<span data-ttu-id="c8899-117">El acceso a elemento `[]` no se considera un operador sobrecargable.</span><span class="sxs-lookup"><span data-stu-id="c8899-117">Element access `[]` is not considered an overloadable operator.</span></span> <span data-ttu-id="c8899-118">Use [indizadores](../../programming-guide/indexers/index.md) para admitir la indización con tipos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c8899-118">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c8899-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c8899-119">C# language specification</span></span>

<span data-ttu-id="c8899-120">Para más información, consulte las secciones [Acceso a elemento](~/_csharplang/spec/expressions.md#element-access) y [Acceso a elemento de puntero](~/_csharplang/spec/unsafe-code.md#pointer-element-access) de la [Especificación de lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c8899-120">For more information, see the [Element access](~/_csharplang/spec/expressions.md#element-access) and [Pointer element access](~/_csharplang/spec/unsafe-code.md#pointer-element-access) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8899-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8899-121">See also</span></span>

- [<span data-ttu-id="c8899-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c8899-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8899-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c8899-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8899-124">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c8899-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="c8899-125">Matrices</span><span class="sxs-lookup"><span data-stu-id="c8899-125">Arrays</span></span>](../../programming-guide/arrays/index.md)
- [<span data-ttu-id="c8899-126">Indizadores</span><span class="sxs-lookup"><span data-stu-id="c8899-126">Indexers</span></span>](../../programming-guide/indexers/index.md)
- [<span data-ttu-id="c8899-127">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="c8899-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="c8899-128">Atributos</span><span class="sxs-lookup"><span data-stu-id="c8899-128">Attributes</span></span>](../../programming-guide/concepts/attributes/index.md)
- <span data-ttu-id="c8899-129">[Operadores ?. y ?[]](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="c8899-129">[?. and ?[] operators](null-conditional-operators.md)</span></span>