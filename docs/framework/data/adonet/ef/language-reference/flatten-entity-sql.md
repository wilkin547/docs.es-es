---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 75463ed622ac969eb2690c4118861823479a2caa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="11477-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="11477-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="11477-103">Convierte una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="11477-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="11477-104">La nueva colección contiene los mismos elementos que la colección anterior, pero sin una estructura anidada.</span><span class="sxs-lookup"><span data-stu-id="11477-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11477-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11477-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="11477-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="11477-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="11477-107">Cualquier expresión válida que devuelva una colección de colecciones de valores para convertir en una sola colección.</span><span class="sxs-lookup"><span data-stu-id="11477-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11477-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11477-108">Remarks</span></span>  
 <span data-ttu-id="11477-109">`FLATTEN` es uno de los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11477-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="11477-110">Todos los operadores de conjuntos de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se evalúan de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="11477-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="11477-111">Vea [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) para obtener información de prioridad para la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operadores de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="11477-111">See [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11477-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11477-112">Example</span></span>  
 <span data-ttu-id="11477-113">La siguiente consulta de Entity SQL usa el operador `FLATTEN` para convertir una colección de colecciones en una colección plana.</span><span class="sxs-lookup"><span data-stu-id="11477-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="11477-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="11477-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="11477-115">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="11477-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="11477-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="11477-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="11477-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="11477-117">See Also</span></span>  
 [<span data-ttu-id="11477-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="11477-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
