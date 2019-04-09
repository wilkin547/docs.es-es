---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 3ceaf33d8baba9776008cddcbe2e2d70f13fe089
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141289"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="cb614-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cb614-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="cb614-103">Combina dos expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="cb614-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb614-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb614-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="cb614-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cb614-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="cb614-106">Cualquier expresión válida que devuelve un valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="cb614-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb614-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cb614-107">Return Value</span></span>  
 `true` <span data-ttu-id="cb614-108">Cuando alguna de las condiciones es `true`; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="cb614-108">when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb614-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb614-109">Remarks</span></span>  
 <span data-ttu-id="cb614-110">OR es un operador lógico de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb614-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="cb614-111">Se usa para combinar dos condiciones.</span><span class="sxs-lookup"><span data-stu-id="cb614-111">It is used to combine two conditions.</span></span> <span data-ttu-id="cb614-112">Cuando se utiliza más de un operador lógico en una instrucción, los operadores OR se evalúan después de los operadores AND.</span><span class="sxs-lookup"><span data-stu-id="cb614-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="cb614-113">Sin embargo, se puede cambiar el orden de evaluación mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="cb614-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="cb614-114">Las dobles barras verticales (&#124;&#124;) tienen la misma funcionalidad que el operador OR.</span><span class="sxs-lookup"><span data-stu-id="cb614-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="cb614-115">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="cb614-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="cb614-116">true</span><span class="sxs-lookup"><span data-stu-id="cb614-116">TRUE</span></span>|<span data-ttu-id="cb614-117">true</span><span class="sxs-lookup"><span data-stu-id="cb614-117">TRUE</span></span>|<span data-ttu-id="cb614-118">true</span><span class="sxs-lookup"><span data-stu-id="cb614-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="cb614-119">true</span><span class="sxs-lookup"><span data-stu-id="cb614-119">TRUE</span></span>|<span data-ttu-id="cb614-120">false</span><span class="sxs-lookup"><span data-stu-id="cb614-120">FALSE</span></span>|<span data-ttu-id="cb614-121">NULL</span><span class="sxs-lookup"><span data-stu-id="cb614-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="cb614-122">true</span><span class="sxs-lookup"><span data-stu-id="cb614-122">TRUE</span></span>|<span data-ttu-id="cb614-123">NULL</span><span class="sxs-lookup"><span data-stu-id="cb614-123">NULL</span></span>|<span data-ttu-id="cb614-124">NULL</span><span class="sxs-lookup"><span data-stu-id="cb614-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cb614-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb614-125">Example</span></span>  
 <span data-ttu-id="cb614-126">La siguiente consulta de Entity SQL usa el operador OR para combinar dos expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="cb614-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="cb614-127">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="cb614-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="cb614-128">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cb614-128">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="cb614-129">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="cb614-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="cb614-130">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="cb614-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="cb614-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb614-131">See also</span></span>

- [<span data-ttu-id="cb614-132">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="cb614-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
