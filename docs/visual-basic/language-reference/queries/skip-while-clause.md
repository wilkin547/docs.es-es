---
title: Skip While (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 47703e445865435f5bf5312c3fe41833ac21aa3f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333141"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="f7b6c-102">Skip While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7b6c-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="f7b6c-103">Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7b6c-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f7b6c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f7b6c-105">Parts</span></span>  
  
|<span data-ttu-id="f7b6c-106">Término</span><span class="sxs-lookup"><span data-stu-id="f7b6c-106">Term</span></span>|<span data-ttu-id="f7b6c-107">Definición</span><span class="sxs-lookup"><span data-stu-id="f7b6c-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="f7b6c-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-108">Required.</span></span> <span data-ttu-id="f7b6c-109">Expresión que representa una condición de la que se van a probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="f7b6c-110">La expresión debe devolver un valor `Boolean` o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7b6c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7b6c-111">Remarks</span></span>  
 <span data-ttu-id="f7b6c-112">La cláusula `Skip While` omite los elementos desde el principio del resultado de una consulta hasta que el `expression` proporcionado devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="f7b6c-113">Después de que `expression` devuelve `false`, la consulta devuelve todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="f7b6c-114">El `expression` se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="f7b6c-115">La cláusula `Skip While` difiere de la cláusula `Where` en que la cláusula `Where` se puede utilizar para excluir todos los elementos de una consulta que no cumplan una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="f7b6c-116">La cláusula `Skip While` excluye los elementos solo hasta la primera vez que la condición no se cumple.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="f7b6c-117">La cláusula `Skip While` es muy útil cuando se trabaja con un resultado de consulta ordenado.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="f7b6c-118">Puede omitir un número específico de resultados desde el principio del resultado de una consulta mediante la cláusula `Skip`.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7b6c-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7b6c-119">Example</span></span>  
 <span data-ttu-id="f7b6c-120">En el ejemplo de código siguiente se usa la cláusula `Skip While` para omitir los resultados hasta que se encuentre el primer cliente de la Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="f7b6c-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f7b6c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7b6c-121">See also</span></span>

- [<span data-ttu-id="f7b6c-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7b6c-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f7b6c-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="f7b6c-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="f7b6c-124">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f7b6c-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="f7b6c-125">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f7b6c-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="f7b6c-126">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f7b6c-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="f7b6c-127">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f7b6c-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="f7b6c-128">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f7b6c-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
