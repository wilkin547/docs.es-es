---
title: EXISTS (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a8e483124205d986ad7a44b47815ed6aa2845744
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="exists-entity-sql"></a><span data-ttu-id="5b872-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5b872-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="5b872-103">Determina si una colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="5b872-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b872-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b872-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="5b872-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5b872-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="5b872-106">Expresión de consulta válida que devuelve una colección.</span><span class="sxs-lookup"><span data-stu-id="5b872-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="5b872-107">NOT</span><span class="sxs-lookup"><span data-stu-id="5b872-107">NOT</span></span>  
 <span data-ttu-id="5b872-108">Especifica que el resultado de EXISTS se niega.</span><span class="sxs-lookup"><span data-stu-id="5b872-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b872-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5b872-109">Return Value</span></span>  
 <span data-ttu-id="5b872-110">`true` si la colección no está vacía; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5b872-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b872-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b872-111">Remarks</span></span>  
 <span data-ttu-id="5b872-112">EXISTS es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b872-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="5b872-113">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="5b872-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="5b872-114">Para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos, vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5b872-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b872-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b872-115">Example</span></span>  
 <span data-ttu-id="5b872-116">La siguiente consulta de Entity SQL usa el operador EXISTS para determinar si la colección está vacía.</span><span class="sxs-lookup"><span data-stu-id="5b872-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="5b872-117">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5b872-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5b872-118">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5b872-118">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5b872-119">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5b872-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5b872-120">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5b872-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="5b872-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b872-121">See Also</span></span>  
 [<span data-ttu-id="5b872-122">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5b872-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
