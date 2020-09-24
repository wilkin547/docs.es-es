---
title: = (Igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 31299670d9f47ed7672b980a3415b8d214463b8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148092"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="37258-102">= (Igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="37258-102">= (Equals) (Entity SQL)</span></span>

<span data-ttu-id="37258-103">Compara la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="37258-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37258-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37258-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="37258-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="37258-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="37258-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="37258-106">Any valid expression.</span></span> <span data-ttu-id="37258-107">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="37258-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="37258-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="37258-108">Result Types</span></span>  

 <span data-ttu-id="37258-109">`true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="37258-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37258-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37258-110">Remarks</span></span>  

 <span data-ttu-id="37258-111">El operador == es equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="37258-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37258-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37258-112">Example</span></span>  

 <span data-ttu-id="37258-113">La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="37258-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="37258-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="37258-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="37258-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37258-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="37258-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="37258-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="37258-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="37258-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="37258-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="37258-118">See also</span></span>

- [<span data-ttu-id="37258-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="37258-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
