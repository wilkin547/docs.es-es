---
title: Skip While (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: a3c0749560d8cea1e46d96298347ce54f0bf9185
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393735"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="e2fdf-102">Skip While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2fdf-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="e2fdf-103">Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2fdf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2fdf-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="e2fdf-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e2fdf-105">Parts</span></span>  
  
|<span data-ttu-id="e2fdf-106">Término</span><span class="sxs-lookup"><span data-stu-id="e2fdf-106">Term</span></span>|<span data-ttu-id="e2fdf-107">Definición</span><span class="sxs-lookup"><span data-stu-id="e2fdf-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="e2fdf-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-108">Required.</span></span> <span data-ttu-id="e2fdf-109">Una expresión que representa una condición para probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="e2fdf-110">La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que debe evaluarse como un `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2fdf-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2fdf-111">Remarks</span></span>  
 <span data-ttu-id="e2fdf-112">El `Skip While` cláusula omite los elementos desde el principio del resultado de una consulta hasta que se ha suministrado `expression` devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="e2fdf-113">Después de `expression` devuelve `false`, la consulta devuelve todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="e2fdf-114">El `expression` se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="e2fdf-115">El `Skip While` cláusula difiere el `Where` cláusula en la que el `Where` cláusula puede usarse para excluir todos los elementos de una consulta que no cumplen una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="e2fdf-116">El `Skip While` cláusula excluye los elementos hasta que la primera vez que no se cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="e2fdf-117">El `Skip While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenada.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="e2fdf-118">Puede omitir un número específico de resultados desde el principio de un resultado de consulta utilizando el `Skip` cláusula.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2fdf-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2fdf-119">Example</span></span>  
 <span data-ttu-id="e2fdf-120">El siguiente ejemplo de código utiliza el `Skip While` cláusula para omitir resultados hasta que se encuentra el primer cliente desde los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="e2fdf-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e2fdf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2fdf-121">See Also</span></span>  
 [<span data-ttu-id="e2fdf-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2fdf-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="e2fdf-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="e2fdf-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="e2fdf-124">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e2fdf-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="e2fdf-125">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e2fdf-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="e2fdf-126">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e2fdf-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="e2fdf-127">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e2fdf-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="e2fdf-128">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e2fdf-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
