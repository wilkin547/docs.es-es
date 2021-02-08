---
description: 'Más información acerca de: FLATTEN (Entity SQL)'
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 3701fbdf481024c799b4cdc6f109bae9fc226609
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786360"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="0c834-103">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0c834-103">FLATTEN (Entity SQL)</span></span>

<span data-ttu-id="0c834-104">Convierte una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="0c834-104">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="0c834-105">La nueva colección contiene los mismos elementos que la colección anterior, pero sin una estructura anidada.</span><span class="sxs-lookup"><span data-stu-id="0c834-105">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c834-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c834-106">Syntax</span></span>  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c834-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0c834-107">Arguments</span></span>  

 `collection`  
 <span data-ttu-id="0c834-108">Cualquier expresión válida que devuelva una colección de colecciones de valores para convertir en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="0c834-108">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c834-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c834-109">Remarks</span></span>  

 <span data-ttu-id="0c834-110">`FLATTEN` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c834-110">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="0c834-111">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="0c834-111">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="0c834-112">Vea [excepto](except-entity-sql.md) para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="0c834-112">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c834-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c834-113">Example</span></span>  

 <span data-ttu-id="0c834-114">La siguiente consulta de Entity SQL usa el operador `FLATTEN` para convertir una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="0c834-114">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="0c834-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0c834-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="0c834-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0c834-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="0c834-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0c834-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="0c834-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c834-118">See also</span></span>

- [<span data-ttu-id="0c834-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0c834-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
