---
title: CASE (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f4e92d9a7c66d176357499bc831f07c56f36c90d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="case-entity-sql"></a><span data-ttu-id="471ad-102">CASE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="471ad-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="471ad-103">Evalúa un conjunto de expresiones `Boolean` para determinar el resultado.</span><span class="sxs-lookup"><span data-stu-id="471ad-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="471ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="471ad-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="471ad-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="471ad-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="471ad-106">Es un marcador de posición que indica que se pueden usar varias cláusulas WHEN `Boolean_expression` THEN `result_expression` .</span><span class="sxs-lookup"><span data-stu-id="471ad-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="471ad-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="471ad-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="471ad-108">Es la expresión devuelta cuando `Boolean_expression` se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="471ad-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="471ad-109">`result expression` es cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="471ad-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="471ad-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="471ad-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="471ad-111">Expresión que se devuelve si ninguna operación de comparación se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="471ad-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="471ad-112">Si se omite este argumento y ninguna comparación se evalúa como `true`, CASE devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="471ad-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="471ad-113">`else_result_expression` es cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="471ad-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="471ad-114">Los tipos de datos de `else_result_expression` y cualquier `result_expression` deben ser iguales o deben ser una conversión implícita.</span><span class="sxs-lookup"><span data-stu-id="471ad-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="471ad-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="471ad-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="471ad-116">Es la expresión `Boolean` que se evalúa cuando se usa el formato CASE buscado.</span><span class="sxs-lookup"><span data-stu-id="471ad-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="471ad-117">`Boolean_expression` es cualquier expresión `Boolean` válida.</span><span class="sxs-lookup"><span data-stu-id="471ad-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="471ad-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="471ad-118">Return Value</span></span>  
 <span data-ttu-id="471ad-119">Devuelve el tipo de prioridad más alto del conjunto de tipos de `result_expression` y de la expresión `else_result_expression`opcional.</span><span class="sxs-lookup"><span data-stu-id="471ad-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="471ad-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="471ad-120">Remarks</span></span>  
 <span data-ttu-id="471ad-121">La expresión case de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se parece a la de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="471ad-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="471ad-122">Puede usar la expresión case para efectuar una serie de pruebas condicionales que permitan determinar qué expresión dará el resultado apropiado.</span><span class="sxs-lookup"><span data-stu-id="471ad-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="471ad-123">Este formato de expresión case se aplica a una serie de una o varias expresiones `Boolean` para determinar la que produce el resultado correcto.</span><span class="sxs-lookup"><span data-stu-id="471ad-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="471ad-124">La función CASE evalúa la `Boolean_expression` de cada cláusula WHEN en el orden especificado, y devuelve la `result_expression` de la primera `Boolean_expression` que se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="471ad-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="471ad-125">Las expresiones restantes no se evalúan.</span><span class="sxs-lookup"><span data-stu-id="471ad-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="471ad-126">Si ninguna `Boolean_expression` se evalúa como `true`, el motor de base de datos devuelve la `else_result_expression` si se especifica una cláusula ELSE, o un valor Null en otro caso.</span><span class="sxs-lookup"><span data-stu-id="471ad-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="471ad-127">Una instrucción CASE no puede devolver un conjunto múltiple.</span><span class="sxs-lookup"><span data-stu-id="471ad-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="471ad-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="471ad-128">Example</span></span>  
 <span data-ttu-id="471ad-129">La siguiente consulta de Entity SQL usa la expresión CASE para evaluar un conjunto de expresiones `Boolean` en orden con el fin de determinar el resultado.</span><span class="sxs-lookup"><span data-stu-id="471ad-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="471ad-130">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="471ad-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="471ad-131">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="471ad-131">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="471ad-132">Siga el procedimiento de [Cómo: ejecutar una consulta que muestra los resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="471ad-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="471ad-133">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="471ad-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="471ad-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="471ad-134">See Also</span></span>  
 [<span data-ttu-id="471ad-135">A CONTINUACIÓN</span><span class="sxs-lookup"><span data-stu-id="471ad-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [<span data-ttu-id="471ad-136">SELECCIONE</span><span class="sxs-lookup"><span data-stu-id="471ad-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [<span data-ttu-id="471ad-137">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="471ad-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
