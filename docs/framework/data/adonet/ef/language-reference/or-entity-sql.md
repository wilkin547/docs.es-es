---
title: '|| (OR) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ba0c376bc0b57013fe4701a1f9e84fdd9a5ed62a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="-or-entity-sql"></a><span data-ttu-id="87ba2-102">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="87ba2-102">|| (OR) (Entity SQL)</span></span>
<span data-ttu-id="87ba2-103">Combina dos expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="87ba2-103">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87ba2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87ba2-104">Syntax</span></span>  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="87ba2-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="87ba2-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="87ba2-106">Cualquier expresión válida que devuelve un valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="87ba2-106">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87ba2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87ba2-107">Return Value</span></span>  
 <span data-ttu-id="87ba2-108">`true` cuando alguna de las condiciones es `true`; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="87ba2-108">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87ba2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87ba2-109">Remarks</span></span>  
 <span data-ttu-id="87ba2-110">OR es un operador lógico de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87ba2-110">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="87ba2-111">Se usa para combinar dos condiciones.</span><span class="sxs-lookup"><span data-stu-id="87ba2-111">It is used to combine two conditions.</span></span> <span data-ttu-id="87ba2-112">Cuando se utiliza más de un operador lógico en una instrucción, los operadores OR se evalúan después de los operadores AND.</span><span class="sxs-lookup"><span data-stu-id="87ba2-112">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="87ba2-113">Sin embargo, se puede cambiar el orden de evaluación mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="87ba2-113">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="87ba2-114">Las dobles barras verticales (&#124; &#124;) tiene la misma funcionalidad que el operador OR.</span><span class="sxs-lookup"><span data-stu-id="87ba2-114">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="87ba2-115">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="87ba2-115">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="87ba2-116">true</span><span class="sxs-lookup"><span data-stu-id="87ba2-116">TRUE</span></span>|<span data-ttu-id="87ba2-117">true</span><span class="sxs-lookup"><span data-stu-id="87ba2-117">TRUE</span></span>|<span data-ttu-id="87ba2-118">true</span><span class="sxs-lookup"><span data-stu-id="87ba2-118">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="87ba2-119">true</span><span class="sxs-lookup"><span data-stu-id="87ba2-119">TRUE</span></span>|<span data-ttu-id="87ba2-120">false</span><span class="sxs-lookup"><span data-stu-id="87ba2-120">FALSE</span></span>|<span data-ttu-id="87ba2-121">NULL</span><span class="sxs-lookup"><span data-stu-id="87ba2-121">NULL</span></span>|  
|`NULL`|<span data-ttu-id="87ba2-122">true</span><span class="sxs-lookup"><span data-stu-id="87ba2-122">TRUE</span></span>|<span data-ttu-id="87ba2-123">NULL</span><span class="sxs-lookup"><span data-stu-id="87ba2-123">NULL</span></span>|<span data-ttu-id="87ba2-124">NULL</span><span class="sxs-lookup"><span data-stu-id="87ba2-124">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="87ba2-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87ba2-125">Example</span></span>  
 <span data-ttu-id="87ba2-126">La siguiente consulta de Entity SQL usa el operador OR para combinar dos expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="87ba2-126">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="87ba2-127">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="87ba2-127">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="87ba2-128">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="87ba2-128">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="87ba2-129">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="87ba2-129">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="87ba2-130">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="87ba2-130">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a><span data-ttu-id="87ba2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="87ba2-131">See Also</span></span>  
 [<span data-ttu-id="87ba2-132">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="87ba2-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
