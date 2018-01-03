---
title: FLATTEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 467277a1697f9f6ca4da7278045cbec34202eed5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="d2e33-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d2e33-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="d2e33-103">Convierte una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="d2e33-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="d2e33-104">La nueva colección contiene los mismos elementos que la colección anterior, pero sin una estructura anidada.</span><span class="sxs-lookup"><span data-stu-id="d2e33-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e33-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2e33-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2e33-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d2e33-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="d2e33-107">Cualquier expresión válida que devuelva una colección de colecciones de valores para convertir en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="d2e33-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2e33-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2e33-108">Remarks</span></span>  
 <span data-ttu-id="d2e33-109">`FLATTEN` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2e33-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d2e33-110">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="d2e33-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d2e33-111">Vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="d2e33-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2e33-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2e33-112">Example</span></span>  
 <span data-ttu-id="d2e33-113">La siguiente consulta de Entity SQL usa el operador `FLATTEN` para convertir una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="d2e33-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="d2e33-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d2e33-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d2e33-115">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d2e33-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d2e33-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d2e33-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="d2e33-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2e33-117">See Also</span></span>  
 [<span data-ttu-id="d2e33-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d2e33-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
