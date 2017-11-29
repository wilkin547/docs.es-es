---
title: = (Igual que) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 12de808403ee6714d2bcfd15da4e67a8596e1ff1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="af2d5-102">= (Igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="af2d5-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="af2d5-103">Compara la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="af2d5-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af2d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af2d5-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="af2d5-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="af2d5-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="af2d5-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="af2d5-106">Any valid expression.</span></span> <span data-ttu-id="af2d5-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="af2d5-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="af2d5-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="af2d5-108">Result Types</span></span>  
 <span data-ttu-id="af2d5-109">`true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="af2d5-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af2d5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af2d5-110">Remarks</span></span>  
 <span data-ttu-id="af2d5-111">El operador == es equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="af2d5-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af2d5-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af2d5-112">Example</span></span>  
 <span data-ttu-id="af2d5-113">La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="af2d5-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="af2d5-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="af2d5-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="af2d5-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="af2d5-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="af2d5-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="af2d5-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="af2d5-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="af2d5-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="af2d5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="af2d5-118">See Also</span></span>  
 [<span data-ttu-id="af2d5-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="af2d5-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
