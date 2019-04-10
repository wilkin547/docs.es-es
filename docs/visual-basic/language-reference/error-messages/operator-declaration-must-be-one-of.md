---
title: 'Declaración de un operador debe ser uno de: +,-, *,-, -, ^, &amp;, Like, Mod y, Or, Xor, no, <<>>,, =, <>, <, < =, >, > =, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 4283547109ec312cc4fe07a054bbb8db3bff660f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299194"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="aaaba-102">Declaración de un operador debe ser uno de: +,-, \*,\,/, ^, &amp;, Like, Mod y, Or, Xor, no, \< \<, >>...</span><span class="sxs-lookup"><span data-stu-id="aaaba-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="aaaba-103">Puede declarar sólo un operador que sea apto para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="aaaba-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="aaaba-104">En la tabla siguiente se enumera los operadores que se puede declarar.</span><span class="sxs-lookup"><span data-stu-id="aaaba-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="aaaba-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="aaaba-105">Type</span></span>|<span data-ttu-id="aaaba-106">Operadores</span><span class="sxs-lookup"><span data-stu-id="aaaba-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="aaaba-107">Unario</span><span class="sxs-lookup"><span data-stu-id="aaaba-107">Unary</span></span>|`+`<span data-ttu-id="aaaba-108">, `-`, `IsFalse`, `IsTrue`,</span><span class="sxs-lookup"><span data-stu-id="aaaba-108">, `-`, `IsFalse`, `IsTrue`,</span></span> `Not`|  
|<span data-ttu-id="aaaba-109">Binary</span><span class="sxs-lookup"><span data-stu-id="aaaba-109">Binary</span></span>|`+`<span data-ttu-id="aaaba-110">, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`,</span><span class="sxs-lookup"><span data-stu-id="aaaba-110">, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`,</span></span> `Xor`|  
|<span data-ttu-id="aaaba-111">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="aaaba-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="aaaba-112">Tenga en cuenta que el `=` operador en la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="aaaba-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="aaaba-113">**Identificador de error:** BC33000</span><span class="sxs-lookup"><span data-stu-id="aaaba-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aaaba-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="aaaba-114">To correct this error</span></span>  
  
1. <span data-ttu-id="aaaba-115">Seleccione un operador del conjunto de operadores sobrecargables.</span><span class="sxs-lookup"><span data-stu-id="aaaba-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="aaaba-116">Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="aaaba-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaaba-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaaba-117">See also</span></span>

- [<span data-ttu-id="aaaba-118">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="aaaba-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="aaaba-119">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="aaaba-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="aaaba-120">Filtrar para definir un operador</span><span class="sxs-lookup"><span data-stu-id="aaaba-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="aaaba-121">Filtrar para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="aaaba-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="aaaba-122">Function (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="aaaba-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
