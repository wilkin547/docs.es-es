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
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45596980"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="26364-102">Operador \* (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="26364-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="26364-103">El operador de multiplicación (`*`) calcula el producto de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="26364-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="26364-104">Todos los tipos numéricos tienen operadores de multiplicación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="26364-104">All numeric types have predefined multiplication operators.</span></span>  

<span data-ttu-id="26364-105">`*` también ejerce de operador de desreferencia, que permite leer y escribir en un puntero.</span><span class="sxs-lookup"><span data-stu-id="26364-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="26364-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26364-106">Remarks</span></span>  
 <span data-ttu-id="26364-107">El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros.</span><span class="sxs-lookup"><span data-stu-id="26364-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="26364-108">Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="26364-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="26364-109">El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="26364-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="26364-110">Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="26364-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="26364-111">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="26364-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26364-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26364-112">Example</span></span>  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="26364-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26364-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="26364-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="26364-114">See Also</span></span>

- [<span data-ttu-id="26364-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="26364-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="26364-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="26364-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="26364-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="26364-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="26364-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="26364-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
