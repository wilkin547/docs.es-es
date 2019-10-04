---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 84b846e3db86c664bc42363f3d983a1001f5c318
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833805"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="5bae0-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5bae0-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="5bae0-103">Convierte una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="5bae0-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="5bae0-104">La nueva colección contiene los mismos elementos que la colección anterior, pero sin una estructura anidada.</span><span class="sxs-lookup"><span data-stu-id="5bae0-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bae0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bae0-105">Syntax</span></span>  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="5bae0-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5bae0-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="5bae0-107">Cualquier expresión válida que devuelva una colección de colecciones de valores para convertir en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="5bae0-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bae0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5bae0-108">Remarks</span></span>  
 <span data-ttu-id="5bae0-109">`FLATTEN` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bae0-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="5bae0-110">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="5bae0-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="5bae0-111">Vea [excepto](except-entity-sql.md) para obtener información sobre la prioridad de los operadores de conjuntos [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bae0-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bae0-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bae0-112">Example</span></span>  
 <span data-ttu-id="5bae0-113">La siguiente consulta de Entity SQL usa el operador `FLATTEN` para convertir una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="5bae0-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="5bae0-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5bae0-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5bae0-115">Siga el procedimiento descrito en [How para: Ejecute una consulta que devuelva los resultados de StructuralType @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="5bae0-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5bae0-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5bae0-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="5bae0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bae0-117">See also</span></span>

- [<span data-ttu-id="5bae0-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5bae0-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
