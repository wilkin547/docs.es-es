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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 27faf6c59afd4de2481f474053812b12182e3f58
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="dc48e-102">= (Igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dc48e-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="dc48e-103">Compara la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="dc48e-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc48e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc48e-104">Syntax</span></span>  
  
```  
expression = expression  
or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="dc48e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dc48e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="dc48e-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="dc48e-106">Any valid expression.</span></span> <span data-ttu-id="dc48e-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="dc48e-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="dc48e-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="dc48e-108">Result Types</span></span>  
 <span data-ttu-id="dc48e-109">`true` si la expresión izquierda es igual a la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="dc48e-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc48e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc48e-110">Remarks</span></span>  
 <span data-ttu-id="dc48e-111">El operador == es equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="dc48e-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc48e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc48e-112">Example</span></span>  
 <span data-ttu-id="dc48e-113">La siguiente consulta de Entity SQL utiliza el operador de comparación = para comparar la igualdad de dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="dc48e-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="dc48e-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="dc48e-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dc48e-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dc48e-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="dc48e-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="dc48e-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="dc48e-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="dc48e-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="dc48e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc48e-118">See Also</span></span>  
 [<span data-ttu-id="dc48e-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dc48e-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
