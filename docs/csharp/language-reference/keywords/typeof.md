---
title: 'typeof: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: f218414bf60a86b95461d747fb6c557f03bcfcb3
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2019
ms.locfileid: "57846121"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="15c8d-102">typeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="15c8d-102">typeof (C# Reference)</span></span>

<span data-ttu-id="15c8d-103">Se usa para obtener el objeto <xref:System.Type?displayProperty=nameWithType> de un tipo.</span><span class="sxs-lookup"><span data-stu-id="15c8d-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="15c8d-104">Una expresión `typeof` tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="15c8d-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="15c8d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15c8d-105">Remarks</span></span>

<span data-ttu-id="15c8d-106">Para obtener el tipo en tiempo de ejecución de una expresión, puede usar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15c8d-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="15c8d-107">El operador `typeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="15c8d-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="15c8d-108">El operador `typeof` también puede usarse en tipos genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="15c8d-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="15c8d-109">Los tipos con más de un parámetro de tipo deben incluir el número correspondiente de comas en la especificación.</span><span class="sxs-lookup"><span data-stu-id="15c8d-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="15c8d-110">Por ejemplo, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> tiene dos argumentos de tipo, por lo que puede usar una coma:</span><span class="sxs-lookup"><span data-stu-id="15c8d-110">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> has two type arguments, so you use one comma:</span></span>

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

<span data-ttu-id="15c8d-111">En el ejemplo siguiente se muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico.</span><span class="sxs-lookup"><span data-stu-id="15c8d-111">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="15c8d-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> devolverá `null` si el tipo de valor devuelto no es un tipo genérico <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="15c8d-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="15c8d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15c8d-113">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="15c8d-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15c8d-114">Example</span></span>

<span data-ttu-id="15c8d-115">En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se usa para contener el resultado de un cálculo numérico.</span><span class="sxs-lookup"><span data-stu-id="15c8d-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="15c8d-116">Esto varía en función de los requisitos de almacenamiento del número resultante.</span><span class="sxs-lookup"><span data-stu-id="15c8d-116">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="15c8d-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="15c8d-117">C# language specification</span></span>

<span data-ttu-id="15c8d-118">Para obtener más información, vea la sección [El operador typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="15c8d-118">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="15c8d-119">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="15c8d-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="15c8d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="15c8d-120">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="15c8d-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="15c8d-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="15c8d-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="15c8d-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="15c8d-123">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="15c8d-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="15c8d-124">is</span><span class="sxs-lookup"><span data-stu-id="15c8d-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="15c8d-125">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="15c8d-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
