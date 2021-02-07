---
description: Más información acerca de:! (NOT) (Entity SQL)
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 648cc4ff73769ae280570b2d42934b2001fa5182
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696456"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="2cb48-105">!</span><span class="sxs-lookup"><span data-stu-id="2cb48-105">!</span></span> <span data-ttu-id="2cb48-106">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2cb48-106">(NOT) (Entity SQL)</span></span>

<span data-ttu-id="2cb48-107">Niega una expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="2cb48-107">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb48-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2cb48-108">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="2cb48-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2cb48-109">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="2cb48-110">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="2cb48-110">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cb48-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2cb48-111">Remarks</span></span>  

 <span data-ttu-id="2cb48-112">El signo de admiración (!) tiene la misma funcionalidad que el operador NOT.</span><span class="sxs-lookup"><span data-stu-id="2cb48-112">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cb48-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cb48-113">Example</span></span>  

 <span data-ttu-id="2cb48-114">La siguiente consulta de Entity SQL usa el operador NOT para negar una expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="2cb48-114">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="2cb48-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="2cb48-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2cb48-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2cb48-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2cb48-117">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2cb48-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2cb48-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2cb48-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="2cb48-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cb48-119">See also</span></span>

- [<span data-ttu-id="2cb48-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2cb48-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
