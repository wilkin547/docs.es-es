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
ms.openlocfilehash: fe6ee470698504bc0434930cc9aa6de712e04254
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004676"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="1e8a5-102">Take While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e8a5-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="1e8a5-103">Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e8a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e8a5-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="1e8a5-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="1e8a5-105">Parts</span></span>  
  
|<span data-ttu-id="1e8a5-106">Término</span><span class="sxs-lookup"><span data-stu-id="1e8a5-106">Term</span></span>|<span data-ttu-id="1e8a5-107">Definición</span><span class="sxs-lookup"><span data-stu-id="1e8a5-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="1e8a5-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-108">Required.</span></span> <span data-ttu-id="1e8a5-109">Expresión que representa una condición de la que se van a probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="1e8a5-110">La expresión debe devolver un valor `Boolean` o un equivalente funcional, como un `Integer` que se va a evaluar como @no__t 2.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e8a5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e8a5-111">Remarks</span></span>  
 <span data-ttu-id="1e8a5-112">La cláusula `Take While` incluye elementos desde el inicio del resultado de una consulta hasta que el `expression` proporcionado devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="1e8a5-113">Después de que el `expression` devuelva `false`, la consulta omitirá todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="1e8a5-114">Se omite el `expression` para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="1e8a5-115">La cláusula `Take While` difiere de la cláusula `Where` en que se puede usar la cláusula `Where` para incluir todos los elementos de una consulta que cumplan una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="1e8a5-116">La cláusula `Take While` solo incluye elementos hasta la primera vez que la condición no se cumple.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="1e8a5-117">La cláusula `Take While` es muy útil cuando se trabaja con un resultado de consulta ordenado.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e8a5-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e8a5-118">Example</span></span>  
 <span data-ttu-id="1e8a5-119">En el ejemplo de código siguiente se usa la cláusula `Take While` para recuperar los resultados hasta que se encuentre el primer cliente sin ningún pedido.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1e8a5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e8a5-120">See also</span></span>

- [<span data-ttu-id="1e8a5-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e8a5-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="1e8a5-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="1e8a5-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="1e8a5-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="1e8a5-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="1e8a5-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="1e8a5-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="1e8a5-125">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="1e8a5-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="1e8a5-126">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="1e8a5-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="1e8a5-127">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="1e8a5-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
