---
title: = (Igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: ec87ec682e1773c001c225567a35b3cedc9c5aba
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251005"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="42e1b-102">= (Igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="42e1b-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="42e1b-103">Compara la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="42e1b-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42e1b-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="42e1b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="42e1b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="42e1b-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="42e1b-106">Any valid expression.</span></span> <span data-ttu-id="42e1b-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="42e1b-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="42e1b-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="42e1b-108">Result Types</span></span>  
 <span data-ttu-id="42e1b-109">`true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="42e1b-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e1b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42e1b-110">Remarks</span></span>  
 <span data-ttu-id="42e1b-111">El operador == es equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="42e1b-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42e1b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42e1b-112">Example</span></span>  
 <span data-ttu-id="42e1b-113">La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="42e1b-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="42e1b-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="42e1b-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="42e1b-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="42e1b-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="42e1b-116">Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.</span><span class="sxs-lookup"><span data-stu-id="42e1b-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="42e1b-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="42e1b-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="42e1b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="42e1b-118">See also</span></span>

- [<span data-ttu-id="42e1b-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="42e1b-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
