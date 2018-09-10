---
title: '* Operador (Referencia de C#)'
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 873cc1dc0d81425117f1784353acf08b35158133
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44225365"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="708bd-102">Operador \* (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="708bd-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="708bd-103">El operador de multiplicación (`*`) calcula el producto de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="708bd-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="708bd-104">Todos los tipos numéricos tienen operadores de multiplicación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="708bd-104">All numeric types have predefined multiplication operators.</span></span>  

<span data-ttu-id="708bd-105">`*` también ejerce de operador de desreferencia, que permite leer y escribir en un puntero.</span><span class="sxs-lookup"><span data-stu-id="708bd-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="708bd-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="708bd-106">Remarks</span></span>  
 <span data-ttu-id="708bd-107">El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros.</span><span class="sxs-lookup"><span data-stu-id="708bd-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="708bd-108">Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="708bd-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="708bd-109">El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="708bd-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="708bd-110">Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="708bd-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="708bd-111">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="708bd-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="708bd-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="708bd-112">Example</span></span>  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="708bd-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="708bd-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="708bd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="708bd-114">See Also</span></span>

- [<span data-ttu-id="708bd-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="708bd-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="708bd-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="708bd-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="708bd-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="708bd-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="708bd-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="708bd-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
