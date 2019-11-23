---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 44f128a292b013fd3a3a80efdd2d10a63e3cfb07
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833837"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="62c9b-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="62c9b-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="62c9b-103">Determina si una colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="62c9b-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c9b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62c9b-104">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="62c9b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="62c9b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="62c9b-106">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="62c9b-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="62c9b-107">NOT</span><span class="sxs-lookup"><span data-stu-id="62c9b-107">NOT</span></span>  
 <span data-ttu-id="62c9b-108">Especifica que el resultado de EXISTS se niega.</span><span class="sxs-lookup"><span data-stu-id="62c9b-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62c9b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62c9b-109">Return Value</span></span>  
 <span data-ttu-id="62c9b-110">`true` si la colección no está vacía; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="62c9b-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c9b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62c9b-111">Remarks</span></span>  
 <span data-ttu-id="62c9b-112">EXISTS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62c9b-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="62c9b-113">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="62c9b-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="62c9b-114">Para obtener información sobre la prioridad de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vea [Except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="62c9b-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="62c9b-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62c9b-115">Example</span></span>  
 <span data-ttu-id="62c9b-116">La siguiente consulta de Entity SQL usa el operador EXISTS para determinar si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="62c9b-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="62c9b-117">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="62c9b-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="62c9b-118">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="62c9b-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="62c9b-119">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="62c9b-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="62c9b-120">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="62c9b-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="62c9b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="62c9b-121">See also</span></span>

- [<span data-ttu-id="62c9b-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="62c9b-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
