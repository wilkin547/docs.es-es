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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946606"
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a><span data-ttu-id="46e99-102">Declaración de un operador debe ser uno de: +,-, \*,\,/, ^, &amp;, Like, Mod y, Or, Xor, no, \< \<, >>...</span><span class="sxs-lookup"><span data-stu-id="46e99-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, \<\<, >>...</span></span>
<span data-ttu-id="46e99-103">Puede declarar sólo un operador que sea apto para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="46e99-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="46e99-104">En la tabla siguiente se enumera los operadores que se puede declarar.</span><span class="sxs-lookup"><span data-stu-id="46e99-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="46e99-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="46e99-105">Type</span></span>|<span data-ttu-id="46e99-106">Operadores</span><span class="sxs-lookup"><span data-stu-id="46e99-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="46e99-107">Unario</span><span class="sxs-lookup"><span data-stu-id="46e99-107">Unary</span></span>|<span data-ttu-id="46e99-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="46e99-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="46e99-109">Binary</span><span class="sxs-lookup"><span data-stu-id="46e99-109">Binary</span></span>|<span data-ttu-id="46e99-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="46e99-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="46e99-111">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="46e99-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="46e99-112">Tenga en cuenta que el `=` operador en la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="46e99-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="46e99-113">**Identificador de error:** BC33000</span><span class="sxs-lookup"><span data-stu-id="46e99-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46e99-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="46e99-114">To correct this error</span></span>  
  
1. <span data-ttu-id="46e99-115">Seleccione un operador del conjunto de operadores sobrecargables.</span><span class="sxs-lookup"><span data-stu-id="46e99-115">Select an operator from the set of overloadable operators.</span></span>  
  
2. <span data-ttu-id="46e99-116">Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="46e99-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e99-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="46e99-117">See also</span></span>

- [<span data-ttu-id="46e99-118">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="46e99-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="46e99-119">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="46e99-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="46e99-120">Cómo: Definir un operador</span><span class="sxs-lookup"><span data-stu-id="46e99-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="46e99-121">Cómo: Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="46e99-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="46e99-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="46e99-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
