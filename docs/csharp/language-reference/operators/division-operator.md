---
title: Operador / (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="49585-102">Operador / (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="49585-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="49585-103">El operador de división (`/`) divide su primer operando por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="49585-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="49585-104">Todos los tipos numéricos tienen operadores de división predefinidos.</span><span class="sxs-lookup"><span data-stu-id="49585-104">All numeric types have predefined division operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49585-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="49585-105">Remarks</span></span>  
 <span data-ttu-id="49585-106">Los tipos definidos por el usuario pueden sobrecargar el operador `/` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="49585-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="49585-107">Una sobrecarga del operador `/` sobrecarga implícitamente el [operador /=](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="49585-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="49585-108">Cuando se dividen dos números enteros, el resultado siempre es un entero.</span><span class="sxs-lookup"><span data-stu-id="49585-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="49585-109">Por ejemplo, el resultado de 7 / 3 es 2.</span><span class="sxs-lookup"><span data-stu-id="49585-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="49585-110">Para determinar el resto de 7 / 3, use el operador de resto ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="49585-110">To determine the remainder of 7 / 3, use the remainder operator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span></span> <span data-ttu-id="49585-111">Para obtener un cociente como un número racional o fracción, asigne al dividendo o al divisor el tipo `float` o el tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="49585-111">To obtain a quotient as a rational number or fraction, give the dividend or divisor type `float` or type `double`.</span></span> <span data-ttu-id="49585-112">Puede asignar el tipo de forma implícita si expresa el dividendo o el divisor como decimal. Para ello, coloque un dígito a la derecha del separador decimal, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="49585-112">You can assign the type implicitly if you express the dividend or divisor as a decimal by putting a digit to the right side of the decimal point, as the following example shows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49585-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49585-113">Example</span></span>  
 <span data-ttu-id="49585-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="49585-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49585-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="49585-115">See Also</span></span>  
 <span data-ttu-id="49585-116">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="49585-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="49585-117">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="49585-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="49585-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="49585-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

