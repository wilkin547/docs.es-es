---
title: Take While (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 7e0a6bd77ca2594e9d74e669fcd9cddf91ee1cad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600915"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="ea180-102">Take While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea180-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="ea180-103">Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="ea180-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea180-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea180-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="ea180-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ea180-105">Parts</span></span>  
  
|<span data-ttu-id="ea180-106">Término</span><span class="sxs-lookup"><span data-stu-id="ea180-106">Term</span></span>|<span data-ttu-id="ea180-107">Definición</span><span class="sxs-lookup"><span data-stu-id="ea180-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="ea180-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="ea180-108">Required.</span></span> <span data-ttu-id="ea180-109">Una expresión que representa una condición para probar los elementos de.</span><span class="sxs-lookup"><span data-stu-id="ea180-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="ea180-110">La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que se debe evaluar como un `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ea180-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea180-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea180-111">Remarks</span></span>  
 <span data-ttu-id="ea180-112">El `Take While` cláusula incluye elementos desde el principio del resultado de una consulta hasta que se ha suministrado `expression` devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="ea180-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="ea180-113">Después de la `expression` devuelve `false`, la consulta omitirá todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="ea180-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="ea180-114">El `expression` se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="ea180-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="ea180-115">El `Take While` cláusula difiere de la `Where` cláusula en la que el `Where` cláusula puede usarse para incluir todos los elementos de una consulta que cumplan una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="ea180-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="ea180-116">El `Take While` cláusula incluye elementos solo hasta que la primera vez que no se cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="ea180-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="ea180-117">El `Take While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenado.</span><span class="sxs-lookup"><span data-stu-id="ea180-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea180-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea180-118">Example</span></span>  
 <span data-ttu-id="ea180-119">El siguiente ejemplo de código utiliza el `Take While` cláusula para recuperar los resultados hasta que se encuentre el primer cliente sin pedidos.</span><span class="sxs-lookup"><span data-stu-id="ea180-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ea180-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea180-120">See Also</span></span>  
 [<span data-ttu-id="ea180-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea180-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="ea180-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="ea180-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="ea180-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ea180-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="ea180-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ea180-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="ea180-125">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ea180-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="ea180-126">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ea180-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="ea180-127">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="ea180-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
