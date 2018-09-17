---
title: + Operador (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: b49694bc8937c58bd295f0f8e57c378802d0dfb9
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45594603"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="df2e6-102">Operador + (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="df2e6-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="df2e6-103">El operador `+` puede funcionar como un operador unario o binario.</span><span class="sxs-lookup"><span data-stu-id="df2e6-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df2e6-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df2e6-104">Remarks</span></span>  
 <span data-ttu-id="df2e6-105">Los operadores unarios `+` están predefinidos para todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="df2e6-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="df2e6-106">El resultado de una operación `+` unaria en un tipo numérico es simplemente el valor del operando.</span><span class="sxs-lookup"><span data-stu-id="df2e6-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="df2e6-107">Los operadores binarios `+` están predefinidos para tipos numéricos y de cadena.</span><span class="sxs-lookup"><span data-stu-id="df2e6-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="df2e6-108">Para los tipos numéricos, + calcula la suma de sus dos operandos.</span><span class="sxs-lookup"><span data-stu-id="df2e6-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="df2e6-109">Cuando uno o ambos operandos son de tipo cadena, + concatena las representaciones de cadena de los operandos.</span><span class="sxs-lookup"><span data-stu-id="df2e6-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="df2e6-110">Los tipos de delegado también proporcionan un operador `+` binario, que realiza la concatenación de delegados.</span><span class="sxs-lookup"><span data-stu-id="df2e6-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="df2e6-111">Los tipos definidos por el usuario pueden sobrecargar los operadores `+` unarios y `+` binarios.</span><span class="sxs-lookup"><span data-stu-id="df2e6-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="df2e6-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="df2e6-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="df2e6-113">Para más información, vea [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="df2e6-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="df2e6-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df2e6-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="df2e6-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="df2e6-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df2e6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="df2e6-116">See Also</span></span>

- [<span data-ttu-id="df2e6-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="df2e6-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="df2e6-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="df2e6-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="df2e6-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="df2e6-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="df2e6-120">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="df2e6-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
