---
title: Operador ++ (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f481dbe2437495b109d6d41cd24c8b4bb5b6a5b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="39451-102">Operador ++ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="39451-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="39451-103">El operador de incremento (`++`) incrementa su operando en 1.</span><span class="sxs-lookup"><span data-stu-id="39451-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="39451-104">El operador de incremento puede aparecer antes o después de su operando: `++variable` y `variable++`.</span><span class="sxs-lookup"><span data-stu-id="39451-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39451-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39451-105">Remarks</span></span>  
 <span data-ttu-id="39451-106">La primera forma es una operación de incremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="39451-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="39451-107">El resultado de la operación es el valor del operando después del incremento.</span><span class="sxs-lookup"><span data-stu-id="39451-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="39451-108">La segunda forma es una operación de incremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="39451-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="39451-109">El resultado de la operación es el valor del operando antes del incremento.</span><span class="sxs-lookup"><span data-stu-id="39451-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="39451-110">Los tipos numéricos y de enumeración poseen operadores de incremento predefinidos.</span><span class="sxs-lookup"><span data-stu-id="39451-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="39451-111">Los tipos definidos por el usuario pueden sobrecargar el operador `++` .</span><span class="sxs-lookup"><span data-stu-id="39451-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="39451-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="39451-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39451-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39451-113">Example</span></span>  
 <span data-ttu-id="39451-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="39451-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39451-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="39451-115">See Also</span></span>  
 <span data-ttu-id="39451-116">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="39451-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="39451-117">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="39451-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="39451-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="39451-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

