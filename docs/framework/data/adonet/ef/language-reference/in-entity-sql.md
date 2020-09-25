---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 582a3b988247f1484197c0905fecf7f4407f88b0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203675"
---
# <a name="in-entity-sql"></a><span data-ttu-id="3b988-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3b988-102">IN (Entity SQL)</span></span>

<span data-ttu-id="3b988-103">Determina si un valor determinado coincide con algún valor de una colección.</span><span class="sxs-lookup"><span data-stu-id="3b988-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b988-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b988-104">Syntax</span></span>  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b988-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3b988-105">Arguments</span></span>  

 `value`  
 <span data-ttu-id="3b988-106">Expresión válida que devuelve el valor que hay que buscar.</span><span class="sxs-lookup"><span data-stu-id="3b988-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="3b988-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="3b988-107">[ NOT ]</span></span>  
 <span data-ttu-id="3b988-108">Especifica que el resultado `Boolean` de IN se niega.</span><span class="sxs-lookup"><span data-stu-id="3b988-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="3b988-109">Expresión válida que devuelve la colección en la que hay que buscar una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="3b988-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="3b988-110">Todas las expresiones deben ser del mismo tipo que `value`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="3b988-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b988-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b988-111">Return Value</span></span>  

 <span data-ttu-id="3b988-112">`true` si el valor se encuentra en la colección; Null si el valor o la colección son Null; `false`, en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="3b988-112">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="3b988-113">El uso de NOT IN niega el resultado de IN.</span><span class="sxs-lookup"><span data-stu-id="3b988-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b988-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b988-114">Example</span></span>  

 <span data-ttu-id="3b988-115">La siguiente consulta de Entity SQL usa el operador IN para determinar si un valor coincide con algún valor de una colección.</span><span class="sxs-lookup"><span data-stu-id="3b988-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="3b988-116">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="3b988-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3b988-117">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3b988-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3b988-118">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="3b988-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="3b988-119">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3b988-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a><span data-ttu-id="3b988-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b988-120">See also</span></span>

- [<span data-ttu-id="3b988-121">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3b988-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
