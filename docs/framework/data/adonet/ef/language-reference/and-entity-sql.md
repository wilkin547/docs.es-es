---
title: '&amp;&amp; ETC (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 86ff43f8ed20c5696d15e21284394c3cb63200e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198046"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="7b035-102">&amp;&amp; ETC (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7b035-102">&amp;&amp; (AND) (Entity SQL)</span></span>

<span data-ttu-id="7b035-103">Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="7b035-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b035-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b035-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="7b035-105">o</span><span class="sxs-lookup"><span data-stu-id="7b035-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="7b035-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7b035-106">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="7b035-107">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="7b035-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b035-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7b035-108">Remarks</span></span>  

 <span data-ttu-id="7b035-109">Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.</span><span class="sxs-lookup"><span data-stu-id="7b035-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="7b035-110">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="7b035-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="7b035-111">TRUE</span><span class="sxs-lookup"><span data-stu-id="7b035-111">TRUE</span></span>|<span data-ttu-id="7b035-112">FALSE</span><span class="sxs-lookup"><span data-stu-id="7b035-112">FALSE</span></span>|<span data-ttu-id="7b035-113">NULL</span><span class="sxs-lookup"><span data-stu-id="7b035-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="7b035-114">false</span><span class="sxs-lookup"><span data-stu-id="7b035-114">FALSE</span></span>|<span data-ttu-id="7b035-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="7b035-115">FALSE</span></span>|<span data-ttu-id="7b035-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="7b035-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="7b035-117">NULL</span><span class="sxs-lookup"><span data-stu-id="7b035-117">NULL</span></span>|<span data-ttu-id="7b035-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="7b035-118">FALSE</span></span>|<span data-ttu-id="7b035-119">NULL</span><span class="sxs-lookup"><span data-stu-id="7b035-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7b035-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b035-120">Example</span></span>  

 <span data-ttu-id="7b035-121">En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND.</span><span class="sxs-lookup"><span data-stu-id="7b035-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="7b035-122">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="7b035-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7b035-123">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="7b035-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7b035-124">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7b035-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="7b035-125">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="7b035-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="7b035-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b035-126">See also</span></span>

- [<span data-ttu-id="7b035-127">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7b035-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
