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
ms.openlocfilehash: 7da5f50a9d0fa867244a569e03685cc637bf3ce6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692524"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="169dc-102">Skip While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="169dc-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="169dc-103">Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="169dc-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="169dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="169dc-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="169dc-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="169dc-105">Parts</span></span>  
  
|<span data-ttu-id="169dc-106">Término</span><span class="sxs-lookup"><span data-stu-id="169dc-106">Term</span></span>|<span data-ttu-id="169dc-107">Definición</span><span class="sxs-lookup"><span data-stu-id="169dc-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="169dc-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="169dc-108">Required.</span></span> <span data-ttu-id="169dc-109">Una expresión que representa una condición para probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="169dc-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="169dc-110">La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que debe evaluarse como un `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="169dc-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="169dc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="169dc-111">Remarks</span></span>  
 <span data-ttu-id="169dc-112">El `Skip While` cláusula omite los elementos desde el principio del resultado de una consulta hasta que se ha suministrado `expression` devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="169dc-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="169dc-113">Después de `expression` devuelve `false`, la consulta devuelve todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="169dc-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="169dc-114">El `expression` se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="169dc-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="169dc-115">El `Skip While` cláusula difiere el `Where` cláusula en la que el `Where` cláusula puede usarse para excluir todos los elementos de una consulta que no cumplen una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="169dc-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="169dc-116">El `Skip While` cláusula excluye los elementos hasta que la primera vez que no se cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="169dc-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="169dc-117">El `Skip While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenada.</span><span class="sxs-lookup"><span data-stu-id="169dc-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="169dc-118">Puede omitir un número específico de resultados desde el principio de un resultado de consulta utilizando el `Skip` cláusula.</span><span class="sxs-lookup"><span data-stu-id="169dc-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="169dc-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="169dc-119">Example</span></span>  
 <span data-ttu-id="169dc-120">El siguiente ejemplo de código utiliza el `Skip While` cláusula para omitir resultados hasta que se encuentra el primer cliente desde los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="169dc-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="169dc-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="169dc-121">See also</span></span>
- [<span data-ttu-id="169dc-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="169dc-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="169dc-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="169dc-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="169dc-124">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="169dc-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="169dc-125">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="169dc-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="169dc-126">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="169dc-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="169dc-127">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="169dc-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="169dc-128">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="169dc-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
