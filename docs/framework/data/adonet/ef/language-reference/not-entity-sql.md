---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 51d3bdbc4adb0b5fd6275629219698dd9b42fa86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306773"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="74f1b-103">!</span><span class="sxs-lookup"><span data-stu-id="74f1b-103">!</span></span> <span data-ttu-id="74f1b-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="74f1b-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="74f1b-105">Niega una expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="74f1b-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f1b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74f1b-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="74f1b-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="74f1b-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="74f1b-108">Cualquier expresión válida que devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="74f1b-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74f1b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74f1b-109">Remarks</span></span>  
 <span data-ttu-id="74f1b-110">El signo de admiración (!) tiene la misma funcionalidad que el operador NOT.</span><span class="sxs-lookup"><span data-stu-id="74f1b-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74f1b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74f1b-111">Example</span></span>  
 <span data-ttu-id="74f1b-112">La siguiente consulta de Entity SQL usa el operador NOT para negar una expresión `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="74f1b-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="74f1b-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="74f1b-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="74f1b-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="74f1b-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="74f1b-115">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="74f1b-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="74f1b-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="74f1b-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="74f1b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="74f1b-117">See also</span></span>

- [<span data-ttu-id="74f1b-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="74f1b-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
