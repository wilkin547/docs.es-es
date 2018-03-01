---
title: "Declaración del operador debe ser uno de: +,-, *,-, -, ^, &amp;, Like, Mod y, Or, Xor, no es así, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;= &gt; , &gt;=, CType, IsTrue, IsFalse"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="47c31-102">Declaración del operador debe ser uno de: +,-, \*,\,/, ^, &amp;, Like, Mod y, Or, Xor, no es así, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="47c31-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="47c31-103">Puede declarar solo un operador que es apto para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="47c31-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="47c31-104">En la tabla siguiente se enumera los operadores que se puede declarar.</span><span class="sxs-lookup"><span data-stu-id="47c31-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="47c31-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="47c31-105">Type</span></span>|<span data-ttu-id="47c31-106">Operadores</span><span class="sxs-lookup"><span data-stu-id="47c31-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="47c31-107">Unario</span><span class="sxs-lookup"><span data-stu-id="47c31-107">Unary</span></span>|<span data-ttu-id="47c31-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="47c31-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="47c31-109">Binary</span><span class="sxs-lookup"><span data-stu-id="47c31-109">Binary</span></span>|<span data-ttu-id="47c31-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="47c31-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="47c31-111">Conversión (unaria)</span><span class="sxs-lookup"><span data-stu-id="47c31-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="47c31-112">Tenga en cuenta que la `=` en la lista binaria es el operador de comparación, no el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="47c31-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="47c31-113">**Id. de error:** BC33000</span><span class="sxs-lookup"><span data-stu-id="47c31-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47c31-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="47c31-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="47c31-115">Seleccione un operador del conjunto de operadores sobrecargables.</span><span class="sxs-lookup"><span data-stu-id="47c31-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="47c31-116">Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="47c31-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c31-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="47c31-117">See Also</span></span>  
 [<span data-ttu-id="47c31-118">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="47c31-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="47c31-119">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="47c31-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="47c31-120">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="47c31-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="47c31-121">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="47c31-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="47c31-122">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="47c31-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
