---
title: '* Operador (Referencia de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
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
ms.openlocfilehash: 165ca8f797eb8d03ae1dec8c0ec5e1f4b31cb050
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="fa29f-102">Operador * (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fa29f-102">* Operator (C# Reference)</span></span>
<span data-ttu-id="fa29f-103">El operador de multiplicación (`*`), que calcula el producto de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="fa29f-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="fa29f-104">Además, el operador de desreferencia, que permite leer y escribir en un puntero.</span><span class="sxs-lookup"><span data-stu-id="fa29f-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa29f-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa29f-105">Remarks</span></span>  
 <span data-ttu-id="fa29f-106">Todos los tipos numéricos tienen operadores de multiplicación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="fa29f-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="fa29f-107">El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros.</span><span class="sxs-lookup"><span data-stu-id="fa29f-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="fa29f-108">Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="fa29f-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="fa29f-109">El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="fa29f-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="fa29f-110">Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="fa29f-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="fa29f-111">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="fa29f-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa29f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa29f-112">Example</span></span>  
 <span data-ttu-id="fa29f-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="fa29f-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa29f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa29f-114">Example</span></span>  
 <span data-ttu-id="fa29f-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="fa29f-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa29f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa29f-116">See Also</span></span>  
 <span data-ttu-id="fa29f-117">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa29f-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fa29f-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa29f-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fa29f-119">[Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="fa29f-119">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 [<span data-ttu-id="fa29f-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="fa29f-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

