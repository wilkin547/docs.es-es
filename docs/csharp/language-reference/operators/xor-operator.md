---
title: Operador ^ (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
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
ms.openlocfilehash: f081dd2979930404639638179444adc05dd462e1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="9fb6e-102">Operador ^ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9fb6e-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="9fb6e-103">Los operadores binarios `^` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="9fb6e-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="9fb6e-104">Para los tipos enteros, `^` calcula OR exclusiva bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="9fb6e-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="9fb6e-105">Para operandos `bool`, `^` calcula OR exclusiva lógica de sus operandos; es decir, el resultado es `true` si y solo si exactamente uno de sus operandos es `true`.</span><span class="sxs-lookup"><span data-stu-id="9fb6e-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fb6e-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9fb6e-106">Remarks</span></span>  
 <span data-ttu-id="9fb6e-107">Los tipos definidos por el usuario pueden sobrecargar el operador `^` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="9fb6e-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="9fb6e-108">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="9fb6e-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fb6e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fb6e-109">Example</span></span>  
 <span data-ttu-id="9fb6e-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9fb6e-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="9fb6e-111">El cálculo de `0xf8 ^ 0x3f` en el ejemplo anterior realiza una operación OR exclusiva bit a bit de los siguientes dos valores binarios, que corresponden a los valores hexadecimales F8 y 3F:</span><span class="sxs-lookup"><span data-stu-id="9fb6e-111">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="9fb6e-112">El resultado de la OR exclusiva es `1100 0111`, que es C7 en hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="9fb6e-112">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb6e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fb6e-113">See Also</span></span>  
 <span data-ttu-id="9fb6e-114">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fb6e-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9fb6e-115">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9fb6e-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9fb6e-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="9fb6e-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

