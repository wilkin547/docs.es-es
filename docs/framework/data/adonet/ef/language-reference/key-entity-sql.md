---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 820d357baf8f3e17a10ced84babc6745512e572b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230036"
---
# <a name="key-entity-sql"></a><span data-ttu-id="5ce3c-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5ce3c-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="5ce3c-103">Extrae la clave de una referencia o de una expresión de entidad.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ce3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ce3c-104">Syntax</span></span>  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="5ce3c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ce3c-105">Remarks</span></span>  
 <span data-ttu-id="5ce3c-106">Una clave de entidad contiene los valores de clave en el orden correcto de la entidad especificada o referencia a entidad.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="5ce3c-107">Dado que varios conjuntos de entidades pueden estar basados en el mismo tipo, la misma clave podría aparecer en cada conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="5ce3c-108">Para obtener una referencia única, utilice `REF`.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="5ce3c-109">El tipo de valor devuelto del operador KEY es un tipo de fila que incluye un campo para cada clave de la entidad, en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="5ce3c-110">En el ejemplo siguiente, al operador Key se le pasa una referencia a la entidad BadOrder y devuelve la parte de la clave de esa referencia.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="5ce3c-111">En este caso, un tipo de registro con exactamente un campo que corresponde a la propiedad `Id` .</span><span class="sxs-lookup"><span data-stu-id="5ce3c-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="5ce3c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ce3c-112">Example</span></span>  
 <span data-ttu-id="5ce3c-113">La consulta de Entity SQL siguiente utiliza el operador KEY para extraer la parte de la clave de una expresión con referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="5ce3c-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="5ce3c-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5ce3c-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5ce3c-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5ce3c-116">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5ce3c-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5ce3c-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5ce3c-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a><span data-ttu-id="5ce3c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ce3c-118">See also</span></span>

- [<span data-ttu-id="5ce3c-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5ce3c-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="5ce3c-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="5ce3c-120">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="5ce3c-121">REF</span><span class="sxs-lookup"><span data-stu-id="5ce3c-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [<span data-ttu-id="5ce3c-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="5ce3c-122">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)
