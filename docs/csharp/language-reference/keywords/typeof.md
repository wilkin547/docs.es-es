---
title: typeof (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 039294d17d25d1d8775e7f92f46f5f57f2ac3212
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146685"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="018c9-102">typeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="018c9-102">typeof (C# Reference)</span></span>

<span data-ttu-id="018c9-103">Se usa para obtener el objeto `System.Type` de un tipo.</span><span class="sxs-lookup"><span data-stu-id="018c9-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="018c9-104">Una expresión `typeof` tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="018c9-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="018c9-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="018c9-105">Remarks</span></span>

<span data-ttu-id="018c9-106">Para obtener el tipo en tiempo de ejecución de una expresión, puede usar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="018c9-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="018c9-107">El operador `typeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="018c9-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="018c9-108">El operador `typeof` también puede usarse en tipos genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="018c9-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="018c9-109">Los tipos con más de un parámetro de tipo deben incluir el número correspondiente de comas en la especificación.</span><span class="sxs-lookup"><span data-stu-id="018c9-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="018c9-110">En el ejemplo siguiente se muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico.</span><span class="sxs-lookup"><span data-stu-id="018c9-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="018c9-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> devolverá `null` si el tipo de valor devuelto no es un tipo genérico <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="018c9-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="018c9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="018c9-112">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="018c9-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="018c9-113">Example</span></span>

<span data-ttu-id="018c9-114">En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se usa para contener el resultado de un cálculo numérico.</span><span class="sxs-lookup"><span data-stu-id="018c9-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="018c9-115">Esto varía en función de los requisitos de almacenamiento del número resultante.</span><span class="sxs-lookup"><span data-stu-id="018c9-115">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="018c9-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="018c9-116">C# language specification</span></span>

<span data-ttu-id="018c9-117">Para obtener más información, vea la sección [El operador typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="018c9-117">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="018c9-118">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="018c9-118">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="018c9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="018c9-119">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="018c9-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="018c9-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="018c9-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="018c9-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="018c9-122">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="018c9-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="018c9-123">is</span><span class="sxs-lookup"><span data-stu-id="018c9-123">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="018c9-124">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="018c9-124">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)