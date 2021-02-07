---
description: 'Más información acerca de: clave (Entity SQL)'
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 83901a378c3bcc92436df734a04cb7fdf639ecb5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748302"
---
# <a name="key-entity-sql"></a><span data-ttu-id="dca83-103">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dca83-103">KEY (Entity SQL)</span></span>

<span data-ttu-id="dca83-104">Extrae la clave de una referencia o de una expresión de entidad.</span><span class="sxs-lookup"><span data-stu-id="dca83-104">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca83-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dca83-105">Syntax</span></span>  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="dca83-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dca83-106">Remarks</span></span>  

 <span data-ttu-id="dca83-107">Una clave de entidad contiene los valores de clave en el orden correcto de la entidad especificada o referencia a entidad.</span><span class="sxs-lookup"><span data-stu-id="dca83-107">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="dca83-108">Dado que varios conjuntos de entidades pueden estar basados en el mismo tipo, la misma clave podría aparecer en cada conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="dca83-108">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="dca83-109">Para obtener una referencia única, utilice `REF`.</span><span class="sxs-lookup"><span data-stu-id="dca83-109">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="dca83-110">El tipo de valor devuelto del operador KEY es un tipo de fila que incluye un campo para cada clave de la entidad, en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="dca83-110">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="dca83-111">En el ejemplo siguiente, al operador Key se le pasa una referencia a la entidad BadOrder y devuelve la parte de la clave de esa referencia.</span><span class="sxs-lookup"><span data-stu-id="dca83-111">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="dca83-112">En este caso, un tipo de registro con exactamente un campo que corresponde a la propiedad `Id` .</span><span class="sxs-lookup"><span data-stu-id="dca83-112">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="dca83-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dca83-113">Example</span></span>  

 <span data-ttu-id="dca83-114">La consulta de Entity SQL siguiente utiliza el operador KEY para extraer la parte de la clave de una expresión con referencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="dca83-114">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="dca83-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="dca83-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dca83-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dca83-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="dca83-117">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="dca83-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="dca83-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="dca83-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a><span data-ttu-id="dca83-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="dca83-119">See also</span></span>

- [<span data-ttu-id="dca83-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dca83-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="dca83-121">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="dca83-121">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="dca83-122">CLI</span><span class="sxs-lookup"><span data-stu-id="dca83-122">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="dca83-123">DEREF</span><span class="sxs-lookup"><span data-stu-id="dca83-123">DEREF</span></span>](deref-entity-sql.md)
