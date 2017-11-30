---
title: '&amp;&amp;(Y) (Entity SQL)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 098f9a09ba4fe114a3ad63f6d98efcd6bb090ac4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="658c4-102">&amp;&amp;(Y) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="658c4-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="658c4-103">Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="658c4-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="658c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="658c4-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="658c4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="658c4-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="658c4-106">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="658c4-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="658c4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="658c4-107">Remarks</span></span>  
 <span data-ttu-id="658c4-108">Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.</span><span class="sxs-lookup"><span data-stu-id="658c4-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="658c4-109">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="658c4-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="658c4-110">true</span><span class="sxs-lookup"><span data-stu-id="658c4-110">TRUE</span></span>|<span data-ttu-id="658c4-111">false</span><span class="sxs-lookup"><span data-stu-id="658c4-111">FALSE</span></span>|<span data-ttu-id="658c4-112">NULL</span><span class="sxs-lookup"><span data-stu-id="658c4-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="658c4-113">false</span><span class="sxs-lookup"><span data-stu-id="658c4-113">FALSE</span></span>|<span data-ttu-id="658c4-114">false</span><span class="sxs-lookup"><span data-stu-id="658c4-114">FALSE</span></span>|<span data-ttu-id="658c4-115">false</span><span class="sxs-lookup"><span data-stu-id="658c4-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="658c4-116">NULL</span><span class="sxs-lookup"><span data-stu-id="658c4-116">NULL</span></span>|<span data-ttu-id="658c4-117">false</span><span class="sxs-lookup"><span data-stu-id="658c4-117">FALSE</span></span>|<span data-ttu-id="658c4-118">NULL</span><span class="sxs-lookup"><span data-stu-id="658c4-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="658c4-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="658c4-119">Example</span></span>  
 <span data-ttu-id="658c4-120">En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND.</span><span class="sxs-lookup"><span data-stu-id="658c4-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="658c4-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="658c4-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="658c4-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="658c4-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="658c4-123">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="658c4-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="658c4-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="658c4-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="658c4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="658c4-125">See Also</span></span>  
 [<span data-ttu-id="658c4-126">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="658c4-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
