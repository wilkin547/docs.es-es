---
title: '. : Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: a59f69d0349a054c8c2a5b701b8f63df113a6580
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333725"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c81d6-103">.</span><span class="sxs-lookup"><span data-stu-id="c81d6-103">.</span></span> <span data-ttu-id="c81d6-104">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c81d6-104">operator (C# Reference)</span></span>

<span data-ttu-id="c81d6-105">El operador punto (`.`) se usa para el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="c81d6-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="c81d6-106">El operador punto especifica un miembro de un tipo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c81d6-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="c81d6-107">Por ejemplo, el operador punto se usa para tener acceso a métodos específicos de las bibliotecas de clases de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c81d6-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>

[!code-csharp[csRefOperators#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#16)]

<span data-ttu-id="c81d6-108">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="c81d6-108">For example, consider the following class:</span></span>

[!code-csharp[csRefOperators#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#17)]

[!code-csharp[csRefOperators#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#18)]

<span data-ttu-id="c81d6-109">La variable `s` tiene dos miembros, `a` y `b`. Para obtener acceso a ellos, use el operador punto:</span><span class="sxs-lookup"><span data-stu-id="c81d6-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>

[!code-csharp[csRefOperators#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#19)]

<span data-ttu-id="c81d6-110">El punto también se usa para formar nombres completos, que son nombres que especifican el espacio de nombres o la interfaz, por ejemplo, a los que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="c81d6-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>

[!code-csharp[csRefOperators#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#20)]

<span data-ttu-id="c81d6-111">La directiva using hace que algunos elementos de calificación de nombres sean opcionales:</span><span class="sxs-lookup"><span data-stu-id="c81d6-111">The using directive makes some name qualification optional:</span></span>

[!code-csharp[csRefOperators#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#21)]

<span data-ttu-id="c81d6-112">Pero cuando un identificador es ambiguo, debe calificarse:</span><span class="sxs-lookup"><span data-stu-id="c81d6-112">But when an identifier is ambiguous, it must be qualified:</span></span>

[!code-csharp[csRefOperators#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="c81d6-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c81d6-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c81d6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c81d6-114">See also</span></span>

- [<span data-ttu-id="c81d6-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c81d6-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c81d6-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c81d6-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c81d6-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c81d6-117">C# Operators</span></span>](index.md)