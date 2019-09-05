---
title: '&amp;&amp;ETC (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 02e404b73e5a9a9c3963e2d2b58ab7592afabc13
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251316"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="94ab8-102">&amp;&amp;ETC (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="94ab8-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="94ab8-103">Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="94ab8-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ab8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94ab8-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="94ab8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="94ab8-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="94ab8-106">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="94ab8-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94ab8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94ab8-107">Remarks</span></span>  
 <span data-ttu-id="94ab8-108">Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.</span><span class="sxs-lookup"><span data-stu-id="94ab8-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="94ab8-109">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="94ab8-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="94ab8-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="94ab8-110">TRUE</span></span>|<span data-ttu-id="94ab8-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="94ab8-111">FALSE</span></span>|<span data-ttu-id="94ab8-112">NULL</span><span class="sxs-lookup"><span data-stu-id="94ab8-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="94ab8-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="94ab8-113">FALSE</span></span>|<span data-ttu-id="94ab8-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="94ab8-114">FALSE</span></span>|<span data-ttu-id="94ab8-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="94ab8-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="94ab8-116">NULL</span><span class="sxs-lookup"><span data-stu-id="94ab8-116">NULL</span></span>|<span data-ttu-id="94ab8-117">false</span><span class="sxs-lookup"><span data-stu-id="94ab8-117">FALSE</span></span>|<span data-ttu-id="94ab8-118">NULL</span><span class="sxs-lookup"><span data-stu-id="94ab8-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94ab8-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94ab8-119">Example</span></span>  
 <span data-ttu-id="94ab8-120">En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND.</span><span class="sxs-lookup"><span data-stu-id="94ab8-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="94ab8-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="94ab8-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="94ab8-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="94ab8-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="94ab8-123">Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.</span><span class="sxs-lookup"><span data-stu-id="94ab8-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="94ab8-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="94ab8-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="94ab8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="94ab8-125">See also</span></span>

- [<span data-ttu-id="94ab8-126">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="94ab8-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
