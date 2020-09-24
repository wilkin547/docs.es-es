---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 36ae2b2b1264150bc66d09366ee33723ed7b28a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166712"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="640ae-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="640ae-102">FLATTEN (Entity SQL)</span></span>

<span data-ttu-id="640ae-103">Convierte una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="640ae-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="640ae-104">La nueva colección contiene los mismos elementos que la colección anterior, pero sin una estructura anidada.</span><span class="sxs-lookup"><span data-stu-id="640ae-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="640ae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="640ae-105">Syntax</span></span>  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="640ae-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="640ae-106">Arguments</span></span>  

 `collection`  
 <span data-ttu-id="640ae-107">Cualquier expresión válida que devuelva una colección de colecciones de valores para convertir en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="640ae-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="640ae-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="640ae-108">Remarks</span></span>  

 <span data-ttu-id="640ae-109">`FLATTEN` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="640ae-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="640ae-110">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="640ae-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="640ae-111">Vea [excepto](except-entity-sql.md) para obtener información sobre la prioridad de los [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="640ae-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="640ae-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="640ae-112">Example</span></span>  

 <span data-ttu-id="640ae-113">La siguiente consulta de Entity SQL usa el operador `FLATTEN` para convertir una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="640ae-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="640ae-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="640ae-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="640ae-115">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="640ae-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="640ae-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="640ae-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="640ae-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="640ae-117">See also</span></span>

- [<span data-ttu-id="640ae-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="640ae-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
