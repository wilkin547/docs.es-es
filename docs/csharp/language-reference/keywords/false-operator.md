---
title: false (Operador, Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f9761fb49e2c7f6e4a7615e64cec9fed88318c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="false-operator-c-reference"></a><span data-ttu-id="6d1d9-102">false (Operador, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6d1d9-102">false Operator (C# Reference)</span></span>
<span data-ttu-id="6d1d9-103">Devuelve el valor [bool](../../../csharp/language-reference/keywords/bool.md) `true` para indicar que un operando es `false` y devuelve `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="6d1d9-103">Returns the [bool](../../../csharp/language-reference/keywords/bool.md) value `true` to indicate that an operand is `false` and returns `false` otherwise.</span></span>  
  
 <span data-ttu-id="6d1d9-104">Antes de C# 2.0, los operadores `true` y `false` se usaban para crear tipos de valor que aceptan valores NULL definidos por el usuario que eran compatibles con tipos como `SqlBool`.</span><span class="sxs-lookup"><span data-stu-id="6d1d9-104">Prior to C# 2.0, the `true` and `false` operators were used to create user-defined nullable value types that were compatible with types such as `SqlBool`.</span></span> <span data-ttu-id="6d1d9-105">Pero ahora este lenguaje proporciona compatibilidad integrada para tipos de valor que aceptan valores NULL y, siempre que sea posible, deben usarse en lugar de sobrecargar los operadores `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="6d1d9-105">However, the language now provides built-in support for nullable value types, and whenever possible you should use those instead of overloading the `true` and `false` operators.</span></span> <span data-ttu-id="6d1d9-106">Para obtener más información, vea [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="6d1d9-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="6d1d9-107">Con valores booleanos que aceptan valores NULL, la expresión `a != b` no es necesariamente igual a `!(a == b)` porque es posible que uno o los dos valores sean NULL.</span><span class="sxs-lookup"><span data-stu-id="6d1d9-107">With nullable Booleans, the expression `a != b` is not necessarily equal to `!(a == b)` because one or both of the values might be null.</span></span> <span data-ttu-id="6d1d9-108">Debe sobrecargar los operadores `true` y `false` por separado para controlar correctamente los valores NULL en la expresión.</span><span class="sxs-lookup"><span data-stu-id="6d1d9-108">You have to overload both the `true` and `false` operators separately to correctly handle the null values in the expression.</span></span> <span data-ttu-id="6d1d9-109">En el ejemplo siguiente se muestra cómo sobrecargar y usar los operadores `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="6d1d9-109">The following example shows how to overload and use the `true` and `false` operators.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]  
  
 <span data-ttu-id="6d1d9-110">Un tipo que sobrecarga los operadores `true` y `false` puede usarse para la expresión de control en instrucciones [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) y [for](../../../csharp/language-reference/keywords/for.md), y en [expresiones condicionales](../../../csharp/language-reference/operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6d1d9-110">A type that overloads the `true` and `false` operators can be used for the controlling expression in [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), and [for](../../../csharp/language-reference/keywords/for.md) statements and in [conditional expressions](../../../csharp/language-reference/operators/conditional-operator.md).</span></span>  
  
 <span data-ttu-id="6d1d9-111">Si un tipo define el operador `false`, también debe definir el operador [true](../../../csharp/language-reference/keywords/true.md).</span><span class="sxs-lookup"><span data-stu-id="6d1d9-111">If a type defines operator `false`, it must also define operator [true](../../../csharp/language-reference/keywords/true.md).</span></span>  
  
 <span data-ttu-id="6d1d9-112">Un tipo no puede sobrecargar directamente los operadores lógicos condicionales [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), pero se consigue un efecto equivalente si se sobrecargan los operadores lógicos normales y los operadores `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="6d1d9-112">A type cannot directly overload the conditional logical operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), but an equivalent effect can be achieved by overloading the regular logical operators and operators `true` and `false`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6d1d9-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6d1d9-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d1d9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d1d9-114">See Also</span></span>  
 [<span data-ttu-id="6d1d9-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6d1d9-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6d1d9-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6d1d9-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6d1d9-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="6d1d9-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6d1d9-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6d1d9-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="6d1d9-119">true</span><span class="sxs-lookup"><span data-stu-id="6d1d9-119">true</span></span>](../../../csharp/language-reference/keywords/true.md)
