---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0b69d4cb64adc1f9232631d50ec42af0d1ba47e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150134"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="54352-103">!</span><span class="sxs-lookup"><span data-stu-id="54352-103">!</span></span> <span data-ttu-id="54352-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="54352-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="54352-105">Niega una expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="54352-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54352-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54352-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="54352-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="54352-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="54352-108">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="54352-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54352-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54352-109">Remarks</span></span>  
 <span data-ttu-id="54352-110">El signo de admiración (!) tiene la misma funcionalidad que el operador NOT.</span><span class="sxs-lookup"><span data-stu-id="54352-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54352-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54352-111">Example</span></span>  
 <span data-ttu-id="54352-112">La siguiente consulta de Entity SQL usa el operador NOT para negar una expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="54352-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="54352-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="54352-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="54352-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="54352-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="54352-115">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="54352-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="54352-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="54352-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="54352-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54352-117">See also</span></span>

- [<span data-ttu-id="54352-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="54352-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
