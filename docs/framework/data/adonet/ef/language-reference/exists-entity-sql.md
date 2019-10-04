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
# <a name="exists-entity-sql"></a><span data-ttu-id="df0be-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="df0be-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="df0be-103">Determina si una colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="df0be-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df0be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df0be-104">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="df0be-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="df0be-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="df0be-106">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="df0be-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="df0be-107">NOT</span><span class="sxs-lookup"><span data-stu-id="df0be-107">NOT</span></span>  
 <span data-ttu-id="df0be-108">Especifica que el resultado de EXISTS se niega.</span><span class="sxs-lookup"><span data-stu-id="df0be-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df0be-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df0be-109">Return Value</span></span>  
 <span data-ttu-id="df0be-110">`true` si la colección no está vacía; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="df0be-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df0be-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df0be-111">Remarks</span></span>  
 <span data-ttu-id="df0be-112">EXISTS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df0be-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="df0be-113">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="df0be-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="df0be-114">Para obtener información sobre la prioridad de los operadores de conjuntos [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vea [Except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="df0be-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="df0be-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df0be-115">Example</span></span>  
 <span data-ttu-id="df0be-116">La siguiente consulta de Entity SQL usa el operador EXISTS para determinar si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="df0be-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="df0be-117">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="df0be-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="df0be-118">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="df0be-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="df0be-119">Siga el procedimiento descrito en [How para: Ejecute una consulta que devuelva los resultados de StructuralType @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="df0be-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="df0be-120">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="df0be-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="df0be-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="df0be-121">See also</span></span>

- [<span data-ttu-id="df0be-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="df0be-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
