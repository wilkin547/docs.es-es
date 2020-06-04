---
title: Cláusula Skip While
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: b357320a92ace1b7a261991737ed653d54d0eeab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359650"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="9b884-102">Skip While (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b884-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="9b884-103">Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="9b884-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b884-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b884-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9b884-105">Partes</span><span class="sxs-lookup"><span data-stu-id="9b884-105">Parts</span></span>  
  
|<span data-ttu-id="9b884-106">Término</span><span class="sxs-lookup"><span data-stu-id="9b884-106">Term</span></span>|<span data-ttu-id="9b884-107">Definición</span><span class="sxs-lookup"><span data-stu-id="9b884-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="9b884-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9b884-108">Required.</span></span> <span data-ttu-id="9b884-109">Expresión que representa una condición de la que se van a probar los elementos.</span><span class="sxs-lookup"><span data-stu-id="9b884-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="9b884-110">La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="9b884-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b884-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9b884-111">Remarks</span></span>  
 <span data-ttu-id="9b884-112">La `Skip While` cláusula omite los elementos desde el principio del resultado de una consulta hasta que el proporcionado `expression` devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="9b884-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="9b884-113">Después `expression` `false` de que devuelva, la consulta devuelve todos los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="9b884-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="9b884-114">`expression`Se omite para los resultados restantes.</span><span class="sxs-lookup"><span data-stu-id="9b884-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="9b884-115">La `Skip While` cláusula difiere de la `Where` cláusula en que la `Where` cláusula se puede utilizar para excluir todos los elementos de una consulta que no cumplan una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="9b884-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="9b884-116">La `Skip While` cláusula excluye los elementos solo hasta la primera vez que la condición no se cumple.</span><span class="sxs-lookup"><span data-stu-id="9b884-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="9b884-117">La `Skip While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenado.</span><span class="sxs-lookup"><span data-stu-id="9b884-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="9b884-118">Puede omitir un número específico de resultados desde el principio del resultado de una consulta mediante la `Skip` cláusula.</span><span class="sxs-lookup"><span data-stu-id="9b884-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b884-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b884-119">Example</span></span>  
 <span data-ttu-id="9b884-120">En el ejemplo de código siguiente `Skip While` se usa la cláusula para omitir los resultados hasta que se encuentre el primer cliente del Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="9b884-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9b884-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b884-121">See also</span></span>

- [<span data-ttu-id="9b884-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b884-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9b884-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="9b884-123">Queries</span></span>](index.md)
- [<span data-ttu-id="9b884-124">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="9b884-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="9b884-125">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="9b884-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="9b884-126">Cláusula Skip</span><span class="sxs-lookup"><span data-stu-id="9b884-126">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="9b884-127">Cláusula Take While</span><span class="sxs-lookup"><span data-stu-id="9b884-127">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="9b884-128">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="9b884-128">Where Clause</span></span>](where-clause.md)
