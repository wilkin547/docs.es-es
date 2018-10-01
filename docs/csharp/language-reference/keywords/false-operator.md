---
title: false (Operador, Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47193793"
---
# <a name="false-operator-c-reference"></a><span data-ttu-id="ab4e5-102">false (Operador, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ab4e5-102">false operator (C# Reference)</span></span>

<span data-ttu-id="ab4e5-103">Devuelve el valor [bool](bool.md) `true` para indicar que un operando es `false` y devuelve `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="ab4e5-103">Returns the [bool](bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>

<span data-ttu-id="ab4e5-104">Antes de C# 2.0, los operadores `true` y `false` se usaban para crear tipos de valor que aceptan valores NULL definidos por el usuario que eran compatibles con tipos como `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="ab4e5-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="ab4e5-105">Pero ahora este lenguaje proporciona compatibilidad integrada para tipos de valor que aceptan valores NULL y, siempre que sea posible, deben usarse en lugar de sobrecargar los operadores `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="ab4e5-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="ab4e5-106">Para obtener más información, vea [Nullable Types](../../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="ab4e5-106">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="ab4e5-107">Con valores booleanos que aceptan valores NULL, la expresión `a != b` no es necesariamente igual a `!(a == b)` porque es posible que uno o los dos valores sean NULL.</span><span class="sxs-lookup"><span data-stu-id="ab4e5-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="ab4e5-108">Debe sobrecargar los operadores `true` y `false` por separado para controlar correctamente los valores NULL en la expresión.</span><span class="sxs-lookup"><span data-stu-id="ab4e5-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="ab4e5-109">En el ejemplo siguiente se muestra cómo sobrecargar y usar los operadores `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="ab4e5-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

<span data-ttu-id="ab4e5-110">Un tipo que sobrecarga los operadores `true` y `false` puede usarse para la expresión de control en instrucciones [if](if-else.md), [do](do.md), [while](while.md) y [for](for.md), y en [expresiones condicionales](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ab4e5-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](if-else.md), [do](do.md), [while](while.md), and [for](for.md) statements and in [conditional expressions](../operators/conditional-operator.md).</span></span>

<span data-ttu-id="ab4e5-111">Si un tipo define el operador `false`, también debe definir el operador [true](true.md).</span><span class="sxs-lookup"><span data-stu-id="ab4e5-111">If a type defines operator `false`, it must also define operator [true](true.md).</span></span>

<span data-ttu-id="ab4e5-112">Un tipo no puede sobrecargar directamente los operadores lógicos condicionales [&&](../operators/conditional-and-operator.md) y [&#124;&#124;](../operators/conditional-or-operator.md), pero se consigue un efecto equivalente si se sobrecargan los operadores lógicos normales y los operadores `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="ab4e5-112">A type cannot directly overload the conditional logical operators [&&](../operators/conditional-and-operator.md) and [&#124;&#124;](../operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ab4e5-113">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ab4e5-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ab4e5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab4e5-114">See also</span></span>

- [<span data-ttu-id="ab4e5-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ab4e5-115">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="ab4e5-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ab4e5-116">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="ab4e5-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ab4e5-117">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="ab4e5-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="ab4e5-118">C# Operators</span></span>](../operators/index.md)  
- [<span data-ttu-id="ab4e5-119">true</span><span class="sxs-lookup"><span data-stu-id="ab4e5-119">true</span></span>](true.md)  