---
title: Take While (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 23b7c84a9f896161a66059fcb1f30753d3b863d5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347109"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="b304b-102">Take While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b304b-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="b304b-103">Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="b304b-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b304b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b304b-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b304b-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="b304b-105">Parts</span></span>  
  
|<span data-ttu-id="b304b-106">Término</span><span class="sxs-lookup"><span data-stu-id="b304b-106">Term</span></span>|<span data-ttu-id="b304b-107">Definición</span><span class="sxs-lookup"><span data-stu-id="b304b-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="b304b-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b304b-108">Required.</span></span> <span data-ttu-id="b304b-109">Expresión que representa una condición de la que se van a probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="b304b-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="b304b-110">La expresión debe devolver un valor `Boolean` o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b304b-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b304b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b304b-111">Remarks</span></span>  
 <span data-ttu-id="b304b-112">La cláusula `Take While` incluye elementos desde el principio del resultado de una consulta hasta que el `expression` proporcionado devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="b304b-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="b304b-113">Una vez que el `expression` devuelva `false`, la consulta omitirá todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="b304b-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="b304b-114">El `expression` se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="b304b-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="b304b-115">La cláusula `Take While` difiere de la cláusula `Where` en que la cláusula `Where` se puede utilizar para incluir todos los elementos de una consulta que cumplan una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="b304b-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="b304b-116">La cláusula `Take While` solo incluye elementos hasta la primera vez que la condición no se cumple.</span><span class="sxs-lookup"><span data-stu-id="b304b-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="b304b-117">La cláusula `Take While` es muy útil cuando se trabaja con un resultado de consulta ordenado.</span><span class="sxs-lookup"><span data-stu-id="b304b-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b304b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b304b-118">Example</span></span>  
 <span data-ttu-id="b304b-119">En el ejemplo de código siguiente se usa la cláusula `Take While` para recuperar los resultados hasta que se encuentre el primer cliente sin ningún pedido.</span><span class="sxs-lookup"><span data-stu-id="b304b-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b304b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b304b-120">See also</span></span>

- [<span data-ttu-id="b304b-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b304b-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b304b-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="b304b-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b304b-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b304b-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b304b-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b304b-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b304b-125">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b304b-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="b304b-126">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b304b-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="b304b-127">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="b304b-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
