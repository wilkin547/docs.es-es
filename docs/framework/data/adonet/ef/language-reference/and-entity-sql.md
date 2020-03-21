---
title: '&amp;&amp;(Y) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eccad616de287a39c42e986cea84dc22feec7f70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150522"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="383b2-102">&amp;&amp;(Y) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="383b2-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="383b2-103">Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="383b2-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="383b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="383b2-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="383b2-105">or</span><span class="sxs-lookup"><span data-stu-id="383b2-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="383b2-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="383b2-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="383b2-107">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="383b2-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="383b2-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="383b2-108">Remarks</span></span>  
 <span data-ttu-id="383b2-109">Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.</span><span class="sxs-lookup"><span data-stu-id="383b2-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="383b2-110">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="383b2-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="383b2-111">TRUE</span><span class="sxs-lookup"><span data-stu-id="383b2-111">TRUE</span></span>|<span data-ttu-id="383b2-112">FALSE</span><span class="sxs-lookup"><span data-stu-id="383b2-112">FALSE</span></span>|<span data-ttu-id="383b2-113">NULL</span><span class="sxs-lookup"><span data-stu-id="383b2-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="383b2-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="383b2-114">FALSE</span></span>|<span data-ttu-id="383b2-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="383b2-115">FALSE</span></span>|<span data-ttu-id="383b2-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="383b2-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="383b2-117">NULL</span><span class="sxs-lookup"><span data-stu-id="383b2-117">NULL</span></span>|<span data-ttu-id="383b2-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="383b2-118">FALSE</span></span>|<span data-ttu-id="383b2-119">NULL</span><span class="sxs-lookup"><span data-stu-id="383b2-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="383b2-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="383b2-120">Example</span></span>  
 <span data-ttu-id="383b2-121">En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND.</span><span class="sxs-lookup"><span data-stu-id="383b2-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="383b2-122">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="383b2-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="383b2-123">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="383b2-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="383b2-124">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="383b2-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="383b2-125">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="383b2-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="383b2-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="383b2-126">See also</span></span>

- [<span data-ttu-id="383b2-127">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="383b2-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
