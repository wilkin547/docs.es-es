---
title: = (Igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: d50ede1964f6d6b9025a7214efe90e878aa55a0c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333163"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="e6a17-102">= (Igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e6a17-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="e6a17-103">Compara la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="e6a17-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6a17-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6a17-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e6a17-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e6a17-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="e6a17-106">Any valid expression.</span></span> <span data-ttu-id="e6a17-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="e6a17-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e6a17-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="e6a17-108">Result Types</span></span>  
 `true` <span data-ttu-id="e6a17-109">Si la expresión izquierda es igual a la expresión derecha; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e6a17-109">if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6a17-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6a17-110">Remarks</span></span>  
 <span data-ttu-id="e6a17-111">El operador == es equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="e6a17-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a17-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6a17-112">Example</span></span>  
 <span data-ttu-id="e6a17-113">La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="e6a17-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="e6a17-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e6a17-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e6a17-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e6a17-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e6a17-116">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e6a17-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e6a17-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e6a17-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a17-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6a17-118">See also</span></span>

- [<span data-ttu-id="e6a17-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e6a17-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
