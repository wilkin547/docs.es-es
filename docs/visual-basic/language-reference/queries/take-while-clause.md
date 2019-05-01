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
ms.openlocfilehash: 080a106fc1deeb54165511ed03d7c7c5d2060f21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945202"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="a30e0-102">Take While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a30e0-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="a30e0-103">Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="a30e0-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a30e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a30e0-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a30e0-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="a30e0-105">Parts</span></span>  
  
|<span data-ttu-id="a30e0-106">Término</span><span class="sxs-lookup"><span data-stu-id="a30e0-106">Term</span></span>|<span data-ttu-id="a30e0-107">Definición</span><span class="sxs-lookup"><span data-stu-id="a30e0-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="a30e0-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a30e0-108">Required.</span></span> <span data-ttu-id="a30e0-109">Una expresión que representa una condición para probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="a30e0-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="a30e0-110">La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que debe evaluarse como un `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="a30e0-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a30e0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a30e0-111">Remarks</span></span>  
 <span data-ttu-id="a30e0-112">El `Take While` cláusula incluye elementos desde el principio de un resultado de consulta hasta que se ha suministrado `expression` devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="a30e0-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="a30e0-113">Después de la `expression` devuelve `false`, la consulta omitirá todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="a30e0-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="a30e0-114">El `expression` se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="a30e0-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="a30e0-115">El `Take While` cláusula difiere el `Where` cláusula en la que el `Where` cláusula puede usarse para incluir todos los elementos de una consulta que cumplen una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="a30e0-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="a30e0-116">El `Take While` cláusula incluye elementos hasta que la primera vez que no se cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="a30e0-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="a30e0-117">El `Take While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenada.</span><span class="sxs-lookup"><span data-stu-id="a30e0-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a30e0-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a30e0-118">Example</span></span>  
 <span data-ttu-id="a30e0-119">El siguiente ejemplo de código utiliza el `Take While` cláusula para recuperar los resultados hasta que se encuentra el primer cliente sin pedidos.</span><span class="sxs-lookup"><span data-stu-id="a30e0-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a30e0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a30e0-120">See also</span></span>

- [<span data-ttu-id="a30e0-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a30e0-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a30e0-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="a30e0-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a30e0-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a30e0-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="a30e0-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a30e0-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="a30e0-125">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a30e0-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="a30e0-126">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a30e0-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="a30e0-127">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a30e0-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
