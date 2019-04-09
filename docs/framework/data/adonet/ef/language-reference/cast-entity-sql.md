---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: afa92cc46aba9def65dddd490a2df3350c163af9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143167"
---
# <a name="cast-entity-sql"></a><span data-ttu-id="b487c-102">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b487c-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="b487c-103">Convierte una expresión de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="b487c-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b487c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b487c-104">Syntax</span></span>  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b487c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b487c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b487c-106">Cualquier expresión válida que se pueda convertir a `data_type`.</span><span class="sxs-lookup"><span data-stu-id="b487c-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="b487c-107">Tipo de datos de destino proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="b487c-107">The target system-supplied data type.</span></span> <span data-ttu-id="b487c-108">Debe ser un tipo (escalar) primitivo.</span><span class="sxs-lookup"><span data-stu-id="b487c-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="b487c-109">El valor de `data_type` usado depende del espacio de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b487c-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="b487c-110">Si se ejecuta una consulta con la clase <xref:System.Data.EntityClient.EntityCommand>, el tipo de datos es un tipo definido en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="b487c-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="b487c-111">Para obtener más información, consulta [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="b487c-111">For more information, see [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span> <span data-ttu-id="b487c-112">Si se ejecuta una consulta con la clase <xref:System.Data.Objects.ObjectQuery%601>, el tipo de datos es un tipo de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b487c-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b487c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b487c-113">Return Value</span></span>  
 <span data-ttu-id="b487c-114">Devuelve el mismo valor que `data_type`.</span><span class="sxs-lookup"><span data-stu-id="b487c-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b487c-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b487c-115">Remarks</span></span>  
 <span data-ttu-id="b487c-116">La expresión de conversión tiene una semántica similar a la expresión CONVERT de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b487c-116">The cast expression has similar semantics to the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT expression.</span></span> <span data-ttu-id="b487c-117">La expresión de conversión se utiliza para convertir un valor de un tipo en un valor de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="b487c-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```  
CAST( e as T )  
```  
  
 <span data-ttu-id="b487c-118">Si e es de un tipo S, y S se puede convertir a T, la expresión anterior es una expresión de conversión válida.</span><span class="sxs-lookup"><span data-stu-id="b487c-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="b487c-119">T debe ser un tipo (escalar) primitivo.</span><span class="sxs-lookup"><span data-stu-id="b487c-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="b487c-120">Se pueden proporcionar opcionalmente valores para las facetas de precisión y escala al convertir a `Edm.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="b487c-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="b487c-121">Si no se proporcionan explícitamente, los valores predeterminados para la precisión y la escala son 18 y 0, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b487c-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="b487c-122">Concretamente, las sobrecargas siguientes son compatibles con `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="b487c-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="b487c-123">El uso de una expresión de conversión se considera una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="b487c-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="b487c-124">Las conversiones explícitas pueden truncar datos o perder precisión.</span><span class="sxs-lookup"><span data-stu-id="b487c-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b487c-125">CAST solo se admite en tipos primitivos y tipos de miembro de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b487c-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b487c-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b487c-126">Example</span></span>  
 <span data-ttu-id="b487c-127">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador CAST para convertir una expresión de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="b487c-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="b487c-128">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b487c-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b487c-129">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b487c-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b487c-130">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b487c-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="b487c-131">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b487c-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="b487c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b487c-132">See also</span></span>

- [<span data-ttu-id="b487c-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b487c-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
