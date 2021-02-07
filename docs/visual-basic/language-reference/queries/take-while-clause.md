---
description: 'Más información sobre: Take while (cláusula, Visual Basic)'
title: Cláusula Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: a413223d4a85670c66f71e24addb92ae4d38a4a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719713"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="6d056-103">Take While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d056-103">Take While Clause (Visual Basic)</span></span>

<span data-ttu-id="6d056-104">Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="6d056-104">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d056-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d056-105">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6d056-106">Partes</span><span class="sxs-lookup"><span data-stu-id="6d056-106">Parts</span></span>  
  
|<span data-ttu-id="6d056-107">Término</span><span class="sxs-lookup"><span data-stu-id="6d056-107">Term</span></span>|<span data-ttu-id="6d056-108">Definición</span><span class="sxs-lookup"><span data-stu-id="6d056-108">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="6d056-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6d056-109">Required.</span></span> <span data-ttu-id="6d056-110">Expresión que representa una condición de la que se van a probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="6d056-110">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="6d056-111">La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="6d056-111">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d056-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6d056-112">Remarks</span></span>  

 <span data-ttu-id="6d056-113">La `Take While` cláusula incluye elementos desde el principio del resultado de una consulta hasta que el proporcionado `expression` devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="6d056-113">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="6d056-114">Una vez que `expression` devuelve `false` , la consulta omitirá todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="6d056-114">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="6d056-115">`expression`Se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="6d056-115">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="6d056-116">La `Take While` cláusula difiere de la `Where` cláusula en que la `Where` cláusula se puede utilizar para incluir todos los elementos de una consulta que cumplan una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="6d056-116">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="6d056-117">La `Take While` cláusula solo incluye elementos hasta la primera vez que la condición no se cumple.</span><span class="sxs-lookup"><span data-stu-id="6d056-117">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="6d056-118">La `Take While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenado.</span><span class="sxs-lookup"><span data-stu-id="6d056-118">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d056-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d056-119">Example</span></span>  

 <span data-ttu-id="6d056-120">En el ejemplo de código siguiente `Take While` se usa la cláusula para recuperar los resultados hasta que se encuentre el primer cliente sin ningún pedido.</span><span class="sxs-lookup"><span data-stu-id="6d056-120">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6d056-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d056-121">See also</span></span>

- [<span data-ttu-id="6d056-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d056-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="6d056-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="6d056-123">Queries</span></span>](index.md)
- [<span data-ttu-id="6d056-124">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6d056-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="6d056-125">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="6d056-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="6d056-126">Cláusula Take</span><span class="sxs-lookup"><span data-stu-id="6d056-126">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="6d056-127">Cláusula Skip While</span><span class="sxs-lookup"><span data-stu-id="6d056-127">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="6d056-128">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="6d056-128">Where Clause</span></span>](where-clause.md)
