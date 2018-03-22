---
title: OVERLAPS (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 22593af3f79e78621764ba293e65505a72b194f8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="02b2f-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="02b2f-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="02b2f-103">Determina si dos colecciones tienen elementos comunes.</span><span class="sxs-lookup"><span data-stu-id="02b2f-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02b2f-104">Syntax</span></span>  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="02b2f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="02b2f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="02b2f-106">Cualquier expresión de consulta válida que devuelva una colección para comparar con la colección que devuelve otra expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="02b2f-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="02b2f-107">Todas las expresiones deben ser del mismo tipo que `expression`o de un tipo base común o derivado.</span><span class="sxs-lookup"><span data-stu-id="02b2f-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02b2f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="02b2f-108">Return Value</span></span>  
 <span data-ttu-id="02b2f-109">`true` si las dos colecciones tienen elementos comunes; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="02b2f-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02b2f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02b2f-110">Remarks</span></span>  
 <span data-ttu-id="02b2f-111">OVERLAPS es funcionalmente equivalente a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="02b2f-111">OVERLAPS provides functionally equivalent tothe following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="02b2f-112">OVERLAPS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02b2f-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="02b2f-113">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="02b2f-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="02b2f-114">Para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="02b2f-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02b2f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02b2f-115">Example</span></span>  
 <span data-ttu-id="02b2f-116">La siguiente consulta de Entity SQL usa el operador OVERLAPS para determinar si dos colecciones tienen un valor común.</span><span class="sxs-lookup"><span data-stu-id="02b2f-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="02b2f-117">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="02b2f-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="02b2f-118">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="02b2f-118">To compile and run this, follow these steps:</span></span>  
  
1.  <span data-ttu-id="02b2f-119">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="02b2f-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="02b2f-120">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="02b2f-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="02b2f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="02b2f-121">See Also</span></span>  
 [<span data-ttu-id="02b2f-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="02b2f-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
