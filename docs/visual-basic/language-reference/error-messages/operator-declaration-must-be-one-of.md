---
title: 'Declaración de un operador debe ser uno de: +,-, *,-, -, ^, &amp;, Like, Mod y, Or, Xor, no, <<>>,, =, <>, <, < =, >, > =, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 7acec56be60f88147bac1ba4179ad0234ea1c6e1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270061"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="9dd04-102">Declaración de un operador debe ser uno de: +,-, \*,\,/, ^, &amp;, Like, Mod y, Or, Xor, no, \< \<, >>...</span><span class="sxs-lookup"><span data-stu-id="9dd04-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="9dd04-103">Puede declarar sólo un operador que sea apto para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="9dd04-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="9dd04-104">En la tabla siguiente se enumera los operadores que se puede declarar.</span><span class="sxs-lookup"><span data-stu-id="9dd04-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="9dd04-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="9dd04-105">Type</span></span>|<span data-ttu-id="9dd04-106">Operadores</span><span class="sxs-lookup"><span data-stu-id="9dd04-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="9dd04-107">Unario</span><span class="sxs-lookup"><span data-stu-id="9dd04-107">Unary</span></span>|<span data-ttu-id="9dd04-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="9dd04-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="9dd04-109">Binary</span><span class="sxs-lookup"><span data-stu-id="9dd04-109">Binary</span></span>|<span data-ttu-id="9dd04-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="9dd04-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="9dd04-111">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="9dd04-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="9dd04-112">Tenga en cuenta que el `=` operador en la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="9dd04-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="9dd04-113">**Identificador de error:** BC33000</span><span class="sxs-lookup"><span data-stu-id="9dd04-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9dd04-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9dd04-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="9dd04-115">Seleccione un operador del conjunto de operadores sobrecargables.</span><span class="sxs-lookup"><span data-stu-id="9dd04-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="9dd04-116">Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="9dd04-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd04-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dd04-117">See also</span></span>
- [<span data-ttu-id="9dd04-118">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9dd04-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="9dd04-119">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="9dd04-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="9dd04-120">Cómo: Definir un operador</span><span class="sxs-lookup"><span data-stu-id="9dd04-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="9dd04-121">Cómo: Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="9dd04-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="9dd04-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9dd04-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
