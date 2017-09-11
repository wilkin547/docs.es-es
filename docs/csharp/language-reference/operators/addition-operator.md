---
title: + Operador (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5455375148f1924c7fe1cdb10e7924abb83a1565
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="d5d59-102">Operador + (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d5d59-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="d5d59-103">El operador `+` puede funcionar como un operador unario o binario.</span><span class="sxs-lookup"><span data-stu-id="d5d59-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5d59-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5d59-104">Remarks</span></span>  
 <span data-ttu-id="d5d59-105">Los operadores unarios `+` están predefinidos para todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="d5d59-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="d5d59-106">El resultado de una operación `+` unaria en un tipo numérico es simplemente el valor del operando.</span><span class="sxs-lookup"><span data-stu-id="d5d59-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="d5d59-107">Los operadores binarios `+` están predefinidos para tipos numéricos y de cadena.</span><span class="sxs-lookup"><span data-stu-id="d5d59-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="d5d59-108">Para los tipos numéricos, + calcula la suma de sus dos operandos.</span><span class="sxs-lookup"><span data-stu-id="d5d59-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="d5d59-109">Cuando uno o ambos operandos son de tipo cadena, + concatena las representaciones de cadena de los operandos.</span><span class="sxs-lookup"><span data-stu-id="d5d59-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="d5d59-110">Los tipos de delegado también proporcionan un operador `+` binario, que realiza la concatenación de delegados.</span><span class="sxs-lookup"><span data-stu-id="d5d59-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="d5d59-111">Los tipos definidos por el usuario pueden sobrecargar los operadores `+` unarios y `+` binarios.</span><span class="sxs-lookup"><span data-stu-id="d5d59-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="d5d59-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="d5d59-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="d5d59-113">Para más información, vea [Operador (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="d5d59-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5d59-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5d59-114">Example</span></span>  
 <span data-ttu-id="d5d59-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5d59-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d5d59-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d5d59-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5d59-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5d59-117">See Also</span></span>  
 <span data-ttu-id="d5d59-118">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5d59-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d5d59-119">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5d59-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d5d59-120">[Operadores de C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5d59-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="d5d59-121">Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d5d59-121">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)

