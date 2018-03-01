---
title: '* Operador (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 64c32def0935f4347f9aaccc2865b9cd33dd8a70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5fbea-102">Operador \* (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5fbea-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="5fbea-103">El operador de multiplicación (`*`), que calcula el producto de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="5fbea-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="5fbea-104">Además, el operador de desreferencia, que permite leer y escribir en un puntero.</span><span class="sxs-lookup"><span data-stu-id="5fbea-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fbea-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fbea-105">Remarks</span></span>  
 <span data-ttu-id="5fbea-106">Todos los tipos numéricos tienen operadores de multiplicación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="5fbea-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="5fbea-107">El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros.</span><span class="sxs-lookup"><span data-stu-id="5fbea-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="5fbea-108">Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5fbea-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="5fbea-109">El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="5fbea-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="5fbea-110">Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="5fbea-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="5fbea-111">Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="5fbea-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fbea-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5fbea-112">Example</span></span>  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="5fbea-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5fbea-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5fbea-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fbea-114">See Also</span></span>  
 [<span data-ttu-id="5fbea-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5fbea-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5fbea-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5fbea-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5fbea-117">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="5fbea-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="5fbea-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="5fbea-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
