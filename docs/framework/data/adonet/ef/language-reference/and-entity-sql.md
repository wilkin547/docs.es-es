---
title: '&amp;&amp; (Y) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eab05f7454f8ebc88ed29030503bfa96d0c70756
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308437"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="e0ca6-102">&amp;&amp; (Y) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e0ca6-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="e0ca6-103">Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="e0ca6-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ca6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0ca6-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e0ca6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e0ca6-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="e0ca6-106">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="e0ca6-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0ca6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0ca6-107">Remarks</span></span>  
 <span data-ttu-id="e0ca6-108">Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.</span><span class="sxs-lookup"><span data-stu-id="e0ca6-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="e0ca6-109">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="e0ca6-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="e0ca6-110">true</span><span class="sxs-lookup"><span data-stu-id="e0ca6-110">TRUE</span></span>|<span data-ttu-id="e0ca6-111">false</span><span class="sxs-lookup"><span data-stu-id="e0ca6-111">FALSE</span></span>|<span data-ttu-id="e0ca6-112">NULL</span><span class="sxs-lookup"><span data-stu-id="e0ca6-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="e0ca6-113">false</span><span class="sxs-lookup"><span data-stu-id="e0ca6-113">FALSE</span></span>|<span data-ttu-id="e0ca6-114">false</span><span class="sxs-lookup"><span data-stu-id="e0ca6-114">FALSE</span></span>|<span data-ttu-id="e0ca6-115">false</span><span class="sxs-lookup"><span data-stu-id="e0ca6-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="e0ca6-116">NULL</span><span class="sxs-lookup"><span data-stu-id="e0ca6-116">NULL</span></span>|<span data-ttu-id="e0ca6-117">false</span><span class="sxs-lookup"><span data-stu-id="e0ca6-117">FALSE</span></span>|<span data-ttu-id="e0ca6-118">NULL</span><span class="sxs-lookup"><span data-stu-id="e0ca6-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0ca6-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0ca6-119">Example</span></span>  
 <span data-ttu-id="e0ca6-120">En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND.</span><span class="sxs-lookup"><span data-stu-id="e0ca6-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="e0ca6-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e0ca6-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e0ca6-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e0ca6-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e0ca6-123">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e0ca6-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e0ca6-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e0ca6-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="e0ca6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0ca6-125">See also</span></span>

- [<span data-ttu-id="e0ca6-126">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e0ca6-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
