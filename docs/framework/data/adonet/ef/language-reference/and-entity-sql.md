---
title: '&amp;&amp; (y) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: be6e7120e6c19714f151aa38a8b9a1355de29d1a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039961"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="6ba01-102">&amp;&amp; (y) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6ba01-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="6ba01-103">Devuelve `true` si las dos expresiones son `true`; en caso contrario, `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="6ba01-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ba01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ba01-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```
 
<span data-ttu-id="6ba01-105">o</span><span class="sxs-lookup"><span data-stu-id="6ba01-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ba01-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ba01-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="6ba01-107">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="6ba01-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ba01-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ba01-108">Remarks</span></span>  
 <span data-ttu-id="6ba01-109">Los caracteres y comercial (&&) tienen la misma funcionalidad que el operador AND.</span><span class="sxs-lookup"><span data-stu-id="6ba01-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="6ba01-110">En la tabla siguiente se muestran los valores de entrada y tipos de valor devuelto posibles.</span><span class="sxs-lookup"><span data-stu-id="6ba01-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="6ba01-111">true</span><span class="sxs-lookup"><span data-stu-id="6ba01-111">TRUE</span></span>|<span data-ttu-id="6ba01-112">false</span><span class="sxs-lookup"><span data-stu-id="6ba01-112">FALSE</span></span>|<span data-ttu-id="6ba01-113">NULL</span><span class="sxs-lookup"><span data-stu-id="6ba01-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="6ba01-114">false</span><span class="sxs-lookup"><span data-stu-id="6ba01-114">FALSE</span></span>|<span data-ttu-id="6ba01-115">false</span><span class="sxs-lookup"><span data-stu-id="6ba01-115">FALSE</span></span>|<span data-ttu-id="6ba01-116">false</span><span class="sxs-lookup"><span data-stu-id="6ba01-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="6ba01-117">NULL</span><span class="sxs-lookup"><span data-stu-id="6ba01-117">NULL</span></span>|<span data-ttu-id="6ba01-118">false</span><span class="sxs-lookup"><span data-stu-id="6ba01-118">FALSE</span></span>|<span data-ttu-id="6ba01-119">NULL</span><span class="sxs-lookup"><span data-stu-id="6ba01-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6ba01-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ba01-120">Example</span></span>  
 <span data-ttu-id="6ba01-121">En la siguiente consulta de Entity SQL se muestra cómo usar el operador AND.</span><span class="sxs-lookup"><span data-stu-id="6ba01-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="6ba01-122">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6ba01-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6ba01-123">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6ba01-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6ba01-124">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6ba01-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6ba01-125">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6ba01-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="6ba01-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ba01-126">See also</span></span>

- [<span data-ttu-id="6ba01-127">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6ba01-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
