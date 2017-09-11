---
title: Operador -- (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
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
ms.openlocfilehash: 100e68f3b07164b0cfb398a32f47137f2726943f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="---operator-c-reference"></a><span data-ttu-id="faa56-102">Operador -- (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="faa56-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="faa56-103">El operador de decremento (`--`) disminuye su operando en 1.</span><span class="sxs-lookup"><span data-stu-id="faa56-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="faa56-104">El operador de decremento puede aparecer antes o después de su operando: `--variable` y `variable--`.</span><span class="sxs-lookup"><span data-stu-id="faa56-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="faa56-105">La primera forma es una operación de decremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="faa56-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="faa56-106">El resultado de la operación es el valor del operando "después" del decremento.</span><span class="sxs-lookup"><span data-stu-id="faa56-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="faa56-107">La segunda forma es una operación de decremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="faa56-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="faa56-108">El resultado de la operación es el valor del operando "antes" del decremento.</span><span class="sxs-lookup"><span data-stu-id="faa56-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faa56-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="faa56-109">Remarks</span></span>  
 <span data-ttu-id="faa56-110">Los tipos numéricos y de enumeración tienen operadores de decremento predefinidos.</span><span class="sxs-lookup"><span data-stu-id="faa56-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="faa56-111">Los tipos definidos por el usuario pueden sobrecargar el operador `--` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="faa56-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="faa56-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="faa56-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="faa56-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="faa56-113">Example</span></span>  
 <span data-ttu-id="faa56-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="faa56-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa56-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="faa56-115">See Also</span></span>  
 <span data-ttu-id="faa56-116">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="faa56-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="faa56-117">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="faa56-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="faa56-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="faa56-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

