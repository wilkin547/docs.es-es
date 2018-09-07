---
title: typeof (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 2493e78fd0782eebee17afd979e1c429339d0a3f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486810"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="ed64d-102">typeof (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ed64d-102">typeof (C# Reference)</span></span>
<span data-ttu-id="ed64d-103">Se usa para obtener el objeto `System.Type` de un tipo.</span><span class="sxs-lookup"><span data-stu-id="ed64d-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="ed64d-104">Una expresión `typeof` tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed64d-104">A `typeof` expression takes the following form:</span></span>  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="ed64d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed64d-105">Remarks</span></span>  
 <span data-ttu-id="ed64d-106">Para obtener el tipo en tiempo de ejecución de una expresión, puede usar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed64d-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="ed64d-107">El operador `typeof` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="ed64d-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="ed64d-108">El operador `typeof` también puede usarse en tipos genéricos abiertos.</span><span class="sxs-lookup"><span data-stu-id="ed64d-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="ed64d-109">Los tipos con más de un parámetro de tipo deben incluir el número correspondiente de comas en la especificación.</span><span class="sxs-lookup"><span data-stu-id="ed64d-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="ed64d-110">En el ejemplo siguiente se muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico.</span><span class="sxs-lookup"><span data-stu-id="ed64d-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="ed64d-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> devolverá `null` si el tipo de valor devuelto no es un tipo genérico <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ed64d-111"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>
  
 [!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]   
  
## <a name="example"></a><span data-ttu-id="ed64d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed64d-112">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="ed64d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed64d-113">Example</span></span>  
 <span data-ttu-id="ed64d-114">En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se usa para contener el resultado de un cálculo numérico.</span><span class="sxs-lookup"><span data-stu-id="ed64d-114">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="ed64d-115">Esto varía en función de los requisitos de almacenamiento del número resultante.</span><span class="sxs-lookup"><span data-stu-id="ed64d-115">This depends on the storage requirements of the resulting number.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ed64d-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ed64d-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed64d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed64d-117">See Also</span></span>

- <xref:System.Type?displayProperty=nameWithType>  
- [<span data-ttu-id="ed64d-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ed64d-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ed64d-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ed64d-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ed64d-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ed64d-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ed64d-121">is</span><span class="sxs-lookup"><span data-stu-id="ed64d-121">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="ed64d-122">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="ed64d-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
