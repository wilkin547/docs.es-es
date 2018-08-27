---
title: implicit (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 70379136fd4b14403eac919ac15590250b17b416
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932736"
---
# <a name="implicit-c-reference"></a><span data-ttu-id="f1d6e-102">implicit (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f1d6e-102">implicit (C# Reference)</span></span>

<span data-ttu-id="f1d6e-103">La palabra clave `implicit` se usa para declarar un operador de conversión de tipo implícito definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f1d6e-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="f1d6e-104">Úsela para permitir conversiones implícitas entre un tipo definido por el usuario y otro tipo, si existen garantías de que la conversión no provocará la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="f1d6e-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>

## <a name="example"></a><span data-ttu-id="f1d6e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1d6e-105">Example</span></span>

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

<span data-ttu-id="f1d6e-106">Si se eliminan las conversiones innecesarias, las conversiones implícitas pueden mejorar la legibilidad del código fuente.</span><span class="sxs-lookup"><span data-stu-id="f1d6e-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="f1d6e-107">En cambio, como las conversiones implícitas no requieren que los programadores conviertan explícitamente un tipo en otro, deben tomarse las medidas adecuadas para impedir que se produzcan resultados imprevistos.</span><span class="sxs-lookup"><span data-stu-id="f1d6e-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="f1d6e-108">En general, los operadores de conversión implícita nunca deberían producir excepciones ni pérdida de información, de modo que puedan usarse de manera segura sin intervención del programador.</span><span class="sxs-lookup"><span data-stu-id="f1d6e-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="f1d6e-109">Si un operador de conversión no cumple esos criterios, debería marcarse como `explicit`.</span><span class="sxs-lookup"><span data-stu-id="f1d6e-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="f1d6e-110">Para obtener más información, vea [Usar operadores de conversión (Guía de programación de C#)](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f1d6e-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f1d6e-111">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f1d6e-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f1d6e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1d6e-112">See also</span></span>

- [<span data-ttu-id="f1d6e-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f1d6e-113">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="f1d6e-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f1d6e-114">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="f1d6e-115">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f1d6e-115">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="f1d6e-116">explicit</span><span class="sxs-lookup"><span data-stu-id="f1d6e-116">explicit</span></span>](explicit.md)  
- [<span data-ttu-id="f1d6e-117">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f1d6e-117">operator (C# Reference)</span></span>](operator.md)  
- [<span data-ttu-id="f1d6e-118">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="f1d6e-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
