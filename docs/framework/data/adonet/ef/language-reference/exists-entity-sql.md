---
description: 'Más información sobre: EXISTs (Entity SQL)'
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: c6c5b86616d63b9cc3389365a96c382101463732
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786386"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="dd52c-103">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dd52c-103">EXISTS (Entity SQL)</span></span>

<span data-ttu-id="dd52c-104">Determina si una colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="dd52c-104">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd52c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd52c-105">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="dd52c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dd52c-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="dd52c-107">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="dd52c-107">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="dd52c-108">NOT</span><span class="sxs-lookup"><span data-stu-id="dd52c-108">NOT</span></span>  
 <span data-ttu-id="dd52c-109">Especifica que el resultado de EXISTS se niega.</span><span class="sxs-lookup"><span data-stu-id="dd52c-109">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd52c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dd52c-110">Return Value</span></span>  

 <span data-ttu-id="dd52c-111">`true` si la colección no está vacía; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="dd52c-111">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd52c-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dd52c-112">Remarks</span></span>  

 <span data-ttu-id="dd52c-113">EXISTS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd52c-113">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="dd52c-114">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="dd52c-114">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="dd52c-115">Para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [excepto](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="dd52c-115">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd52c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd52c-116">Example</span></span>  

 <span data-ttu-id="dd52c-117">La siguiente consulta de Entity SQL usa el operador EXISTS para determinar si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="dd52c-117">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="dd52c-118">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="dd52c-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dd52c-119">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dd52c-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="dd52c-120">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="dd52c-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="dd52c-121">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="dd52c-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="dd52c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd52c-122">See also</span></span>

- [<span data-ttu-id="dd52c-123">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dd52c-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
