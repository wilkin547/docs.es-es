---
title: = (Igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 5cdfd35450514a9699a39cf78f64c0fa6b7d5f39
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833849"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="2c32d-102">= (Igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2c32d-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="2c32d-103">Compara la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="2c32d-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c32d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c32d-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2c32d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2c32d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2c32d-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="2c32d-106">Any valid expression.</span></span> <span data-ttu-id="2c32d-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="2c32d-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2c32d-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="2c32d-108">Result Types</span></span>  
 <span data-ttu-id="2c32d-109">`true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2c32d-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c32d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c32d-110">Remarks</span></span>  
 <span data-ttu-id="2c32d-111">El operador == es equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="2c32d-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c32d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c32d-112">Example</span></span>  
 <span data-ttu-id="2c32d-113">La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="2c32d-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="2c32d-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="2c32d-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2c32d-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2c32d-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2c32d-116">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="2c32d-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2c32d-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="2c32d-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="2c32d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c32d-118">See also</span></span>

- [<span data-ttu-id="2c32d-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="2c32d-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
