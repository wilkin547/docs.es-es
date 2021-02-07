---
description: 'Más información acerca de: &amp; &amp; (y) (Entity SQL)'
title: '&amp;&amp; ETC (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 14fc6bc3f58ac78cb9806a7f421db87bbad048ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697184"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="ec87a-103">&amp;&amp; ETC (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ec87a-103">&amp;&amp; (AND) (Entity SQL)</span></span>

<span data-ttu-id="ec87a-104">Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="ec87a-104">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec87a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec87a-105">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="ec87a-106">o</span><span class="sxs-lookup"><span data-stu-id="ec87a-106">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec87a-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ec87a-107">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="ec87a-108">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="ec87a-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec87a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec87a-109">Remarks</span></span>  

 <span data-ttu-id="ec87a-110">Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.</span><span class="sxs-lookup"><span data-stu-id="ec87a-110">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="ec87a-111">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="ec87a-111">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="ec87a-112">true</span><span class="sxs-lookup"><span data-stu-id="ec87a-112">TRUE</span></span>|<span data-ttu-id="ec87a-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="ec87a-113">FALSE</span></span>|<span data-ttu-id="ec87a-114">NULL</span><span class="sxs-lookup"><span data-stu-id="ec87a-114">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="ec87a-115">false</span><span class="sxs-lookup"><span data-stu-id="ec87a-115">FALSE</span></span>|<span data-ttu-id="ec87a-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="ec87a-116">FALSE</span></span>|<span data-ttu-id="ec87a-117">FALSE</span><span class="sxs-lookup"><span data-stu-id="ec87a-117">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="ec87a-118">NULL</span><span class="sxs-lookup"><span data-stu-id="ec87a-118">NULL</span></span>|<span data-ttu-id="ec87a-119">FALSE</span><span class="sxs-lookup"><span data-stu-id="ec87a-119">FALSE</span></span>|<span data-ttu-id="ec87a-120">NULL</span><span class="sxs-lookup"><span data-stu-id="ec87a-120">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ec87a-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec87a-121">Example</span></span>  

 <span data-ttu-id="ec87a-122">En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND.</span><span class="sxs-lookup"><span data-stu-id="ec87a-122">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="ec87a-123">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="ec87a-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ec87a-124">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec87a-124">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ec87a-125">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ec87a-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ec87a-126">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ec87a-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="ec87a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec87a-127">See also</span></span>

- [<span data-ttu-id="ec87a-128">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ec87a-128">Entity SQL Reference</span></span>](entity-sql-reference.md)
