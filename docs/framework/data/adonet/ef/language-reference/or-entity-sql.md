---
description: 'Más información acerca de: | | DE (Entity SQL)'
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 83af0211de1dd86b057237c36312e3ce33a3512a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696339"
---
# <a name="-or-entity-sql"></a><span data-ttu-id="8903b-103">|| (OR) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8903b-103">|| (OR) (Entity SQL)</span></span>

<span data-ttu-id="8903b-104">Combina dos expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8903b-104">Combines two `Boolean` expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8903b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8903b-105">Syntax</span></span>  
  
```sql  
boolean_expression OR boolean_expression  
-- or
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8903b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8903b-106">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="8903b-107">Cualquier expresión válida que devuelve un valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8903b-107">Any valid expression that returns a `Boolean`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8903b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8903b-108">Return Value</span></span>  

 <span data-ttu-id="8903b-109">`true` cuando alguna de las condiciones es `true`; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="8903b-109">`true` when either of the conditions is `true`; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8903b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8903b-110">Remarks</span></span>  

 <span data-ttu-id="8903b-111">OR es un operador lógico de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8903b-111">OR is an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] logical operator.</span></span> <span data-ttu-id="8903b-112">Se usa para combinar dos condiciones.</span><span class="sxs-lookup"><span data-stu-id="8903b-112">It is used to combine two conditions.</span></span> <span data-ttu-id="8903b-113">Cuando en una instrucción se utiliza más de un operador lógico, los operadores OR se evalúan después de los operadores AND.</span><span class="sxs-lookup"><span data-stu-id="8903b-113">When more than one logical operator is used in a statement, OR operators are evaluated after AND operators.</span></span> <span data-ttu-id="8903b-114">Sin embargo, se puede cambiar el orden de evaluación gracias a los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8903b-114">However, you can change the order of evaluation by using parentheses.</span></span>  
  
 <span data-ttu-id="8903b-115">Las barras verticales dobles (&#124;&#124;) tienen la misma funcionalidad que el operador o.</span><span class="sxs-lookup"><span data-stu-id="8903b-115">Double vertical bars (&#124;&#124;) have the same functionality as the OR operator.</span></span>  
  
 <span data-ttu-id="8903b-116">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="8903b-116">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="8903b-117">TRUE</span><span class="sxs-lookup"><span data-stu-id="8903b-117">TRUE</span></span>|<span data-ttu-id="8903b-118">TRUE</span><span class="sxs-lookup"><span data-stu-id="8903b-118">TRUE</span></span>|<span data-ttu-id="8903b-119">TRUE</span><span class="sxs-lookup"><span data-stu-id="8903b-119">TRUE</span></span>|  
|`FALSE`|<span data-ttu-id="8903b-120">TRUE</span><span class="sxs-lookup"><span data-stu-id="8903b-120">TRUE</span></span>|<span data-ttu-id="8903b-121">FALSE</span><span class="sxs-lookup"><span data-stu-id="8903b-121">FALSE</span></span>|<span data-ttu-id="8903b-122">NULL</span><span class="sxs-lookup"><span data-stu-id="8903b-122">NULL</span></span>|  
|`NULL`|<span data-ttu-id="8903b-123">TRUE</span><span class="sxs-lookup"><span data-stu-id="8903b-123">TRUE</span></span>|<span data-ttu-id="8903b-124">NULL</span><span class="sxs-lookup"><span data-stu-id="8903b-124">NULL</span></span>|<span data-ttu-id="8903b-125">NULL</span><span class="sxs-lookup"><span data-stu-id="8903b-125">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8903b-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8903b-126">Example</span></span>  

 <span data-ttu-id="8903b-127">La siguiente consulta de Entity SQL usa el operador OR para combinar dos expresiones `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8903b-127">The following Entity SQL query uses the OR operator to combine two `Boolean` expressions.</span></span> <span data-ttu-id="8903b-128">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="8903b-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8903b-129">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8903b-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8903b-130">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8903b-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8903b-131">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8903b-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a><span data-ttu-id="8903b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8903b-132">See also</span></span>

- [<span data-ttu-id="8903b-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8903b-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
