---
title: 'Operador ^: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: f6f09f197502af1bc38bcdef97dd1db0ad9c7c08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236952"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="78f85-102">Operador ^ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="78f85-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="78f85-103">Los operadores binarios `^` están predefinidos para los tipos enteros y `bool`.</span><span class="sxs-lookup"><span data-stu-id="78f85-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="78f85-104">Para los tipos enteros, `^` calcula OR exclusiva bit a bit de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="78f85-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="78f85-105">Para operandos `bool`, `^` calcula OR exclusiva lógica de sus operandos; es decir, el resultado es `true` si y solo si exactamente uno de sus operandos es `true`.</span><span class="sxs-lookup"><span data-stu-id="78f85-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78f85-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78f85-106">Remarks</span></span>  
 <span data-ttu-id="78f85-107">Los tipos definidos por el usuario pueden sobrecargar el operador `^` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="78f85-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="78f85-108">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="78f85-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78f85-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78f85-109">Example</span></span>  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 <span data-ttu-id="78f85-110">El cálculo de `0xf8 ^ 0x3f` en el ejemplo anterior realiza una operación OR exclusiva bit a bit de los siguientes dos valores binarios, que corresponden a los valores hexadecimales F8 y 3F:</span><span class="sxs-lookup"><span data-stu-id="78f85-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="78f85-111">El resultado de la OR exclusiva es `1100 0111`, que es C7 en hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="78f85-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f85-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="78f85-112">See Also</span></span>

- [<span data-ttu-id="78f85-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="78f85-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="78f85-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="78f85-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="78f85-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="78f85-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
