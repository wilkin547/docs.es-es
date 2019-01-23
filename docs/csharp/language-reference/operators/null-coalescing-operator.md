---
title: '?? operador: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: b96fe4790aac7ff5ff5394cbaaeaddc1e334e96c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333218"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c8f91-103">??</span><span class="sxs-lookup"><span data-stu-id="c8f91-103">??</span></span> <span data-ttu-id="c8f91-104">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c8f91-104">operator (C# Reference)</span></span>

<span data-ttu-id="c8f91-105">Al operador `??` se le llama el operador de uso combinado de NULL.</span><span class="sxs-lookup"><span data-stu-id="c8f91-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="c8f91-106">Dicho operador devuelve el operando izquierdo si no es NULL; de lo contrario, devuelve el operando derecho.</span><span class="sxs-lookup"><span data-stu-id="c8f91-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8f91-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8f91-107">Remarks</span></span>

<span data-ttu-id="c8f91-108">Un tipo que acepta valores NULL puede representar un valor del dominio del tipo, o el valor puede no estar definido (en cuyo caso el valor es NULL).</span><span class="sxs-lookup"><span data-stu-id="c8f91-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="c8f91-109">Se puede usar la expresividad sintáctica del operador `??` para devolver un valor apropiado (el operando derecho) cuando el operando izquierdo tenga un tipo que acepta valores NULL cuyo valor sea NULL.</span><span class="sxs-lookup"><span data-stu-id="c8f91-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="c8f91-110">Si se intenta asignar un tipo de valor que acepta valores NULL a otro que no sin usar el operador `??`, se generará un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="c8f91-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="c8f91-111">Si se usa una conversión y el tipo de valor que acepta valores NULL no está definido actualmente, se producirá una excepción `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="c8f91-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>

<span data-ttu-id="c8f91-112">Para más información, vea [Tipos que aceptan valores NULL](../../programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="c8f91-112">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="c8f91-113">El resultado de un</span><span class="sxs-lookup"><span data-stu-id="c8f91-113">The result of a ??</span></span> <span data-ttu-id="c8f91-114">operador ?? no se considera una constante, incluso si sus dos argumentos son constantes.</span><span class="sxs-lookup"><span data-stu-id="c8f91-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>

## <a name="example"></a><span data-ttu-id="c8f91-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8f91-115">Example</span></span>

[!code-csharp[csRefOperators#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#53)]

## <a name="c-language-specification"></a><span data-ttu-id="c8f91-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c8f91-116">C# language specification</span></span>

<span data-ttu-id="c8f91-117">Para obtener más información, vea la sección [El operador de uso combinado de NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="c8f91-117">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="c8f91-118">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="c8f91-118">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8f91-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f91-119">See also</span></span>

- [<span data-ttu-id="c8f91-120">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c8f91-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8f91-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c8f91-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8f91-122">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c8f91-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="c8f91-123">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="c8f91-123">Nullable Types</span></span>](../../programming-guide/nullable-types/index.md)
- [<span data-ttu-id="c8f91-124">¿Qué significa exactamente "elevado"?</span><span class="sxs-lookup"><span data-stu-id="c8f91-124">What Exactly Does 'Lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)