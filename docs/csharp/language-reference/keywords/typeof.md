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
ms.openlocfilehash: 3fa82a6faee345be77fc8ea3f5aa3342adecb0f5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244848"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="9456f-102">typeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9456f-102">typeof (C# Reference)</span></span>

<span data-ttu-id="9456f-103">Se usa para obtener el objeto <xref:System.Type?displayProperty=nameWithType> de un tipo.</span><span class="sxs-lookup"><span data-stu-id="9456f-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="9456f-104">Una expresión `typeof` tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="9456f-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="9456f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9456f-105">Remarks</span></span>

<span data-ttu-id="9456f-106">Para obtener el tipo en tiempo de ejecución de una expresión, puede usar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9456f-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="9456f-107">El operador `typeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="9456f-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="9456f-108">El operador `typeof` también puede usarse en tipos genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="9456f-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="9456f-109">Los tipos con más de un parámetro de tipo deben incluir el número correspondiente de comas en la especificación.</span><span class="sxs-lookup"><span data-stu-id="9456f-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="9456f-110">En el ejemplo siguiente se muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico.</span><span class="sxs-lookup"><span data-stu-id="9456f-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="9456f-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> devolverá `null` si el tipo de valor devuelto no es un tipo genérico <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="9456f-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="9456f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9456f-112">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="9456f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9456f-113">Example</span></span>

<span data-ttu-id="9456f-114">En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se usa para contener el resultado de un cálculo numérico.</span><span class="sxs-lookup"><span data-stu-id="9456f-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="9456f-115">Esto varía en función de los requisitos de almacenamiento del número resultante.</span><span class="sxs-lookup"><span data-stu-id="9456f-115">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="9456f-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9456f-116">C# language specification</span></span>

<span data-ttu-id="9456f-117">Para obtener más información, vea la sección [El operador typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="9456f-117">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="9456f-118">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="9456f-118">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="9456f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9456f-119">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="9456f-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9456f-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="9456f-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9456f-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9456f-122">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="9456f-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="9456f-123">is</span><span class="sxs-lookup"><span data-stu-id="9456f-123">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="9456f-124">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="9456f-124">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)