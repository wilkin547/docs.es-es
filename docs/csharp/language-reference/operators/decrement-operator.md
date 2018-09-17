---
title: Operador -- (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 615b100447233856ab3740d075d69e3ae19285fd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45648787"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="0ffc6-102">Operador -- (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0ffc6-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="0ffc6-103">El operador de decremento (`--`) disminuye su operando en 1.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="0ffc6-104">El operador de decremento puede aparecer antes o después de su operando: `--variable` y `variable--`.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="0ffc6-105">La primera forma es una operación de decremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="0ffc6-106">El resultado de la operación es el valor del operando "después" del decremento.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="0ffc6-107">La segunda forma es una operación de decremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="0ffc6-108">El resultado de la operación es el valor del operando "antes" del decremento.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ffc6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ffc6-109">Remarks</span></span>  
 <span data-ttu-id="0ffc6-110">Los tipos numéricos y de enumeración tienen operadores de decremento predefinidos.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="0ffc6-111">Los tipos definidos por el usuario pueden sobrecargar el operador `--` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="0ffc6-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="0ffc6-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0ffc6-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ffc6-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ffc6-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0ffc6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ffc6-114">See Also</span></span>

- [<span data-ttu-id="0ffc6-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0ffc6-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0ffc6-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0ffc6-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0ffc6-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="0ffc6-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
