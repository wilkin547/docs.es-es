---
description: 'Más información acerca de: CAST (Entity SQL)'
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: f6a90c0ec2557391c2da6e46511a020f90d32ab7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739487"
---
# <a name="cast-entity-sql"></a><span data-ttu-id="05441-103">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="05441-103">CAST (Entity SQL)</span></span>

<span data-ttu-id="05441-104">Convierte una expresión de un tipo de datos en otro.</span><span class="sxs-lookup"><span data-stu-id="05441-104">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05441-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05441-105">Syntax</span></span>  
  
```csharp
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="05441-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="05441-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="05441-107">Cualquier expresión válida que se pueda convertir a `data_type`.</span><span class="sxs-lookup"><span data-stu-id="05441-107">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="05441-108">Tipo de datos de destino proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="05441-108">The target system-supplied data type.</span></span> <span data-ttu-id="05441-109">Debe ser un tipo (escalar) primitivo.</span><span class="sxs-lookup"><span data-stu-id="05441-109">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="05441-110">El valor de `data_type` usado depende del espacio de la consulta.</span><span class="sxs-lookup"><span data-stu-id="05441-110">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="05441-111">Si se ejecuta una consulta con la clase <xref:System.Data.EntityClient.EntityCommand>, el tipo de datos es un tipo definido en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="05441-111">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="05441-112">Para obtener más información, consulta [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span><span class="sxs-lookup"><span data-stu-id="05441-112">For more information, see [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span></span> <span data-ttu-id="05441-113">Si se ejecuta una consulta con la clase <xref:System.Data.Objects.ObjectQuery%601>, el tipo de datos es un tipo de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="05441-113">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05441-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="05441-114">Return Value</span></span>  

 <span data-ttu-id="05441-115">Devuelve el mismo valor que `data_type`.</span><span class="sxs-lookup"><span data-stu-id="05441-115">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05441-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="05441-116">Remarks</span></span>  

 <span data-ttu-id="05441-117">La expresión de conversión tiene una semántica similar a la expresión CONVERT de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="05441-117">The cast expression has similar semantics to the Transact-SQL CONVERT expression.</span></span> <span data-ttu-id="05441-118">La expresión de conversión se utiliza para convertir un valor de un tipo en un valor de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="05441-118">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```csharp
CAST( e as T )  
```  
  
 <span data-ttu-id="05441-119">Si e es de un tipo S, y S se puede convertir a T, la expresión anterior es una expresión de conversión válida.</span><span class="sxs-lookup"><span data-stu-id="05441-119">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="05441-120">T debe ser un tipo (escalar) primitivo.</span><span class="sxs-lookup"><span data-stu-id="05441-120">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="05441-121">Se pueden proporcionar opcionalmente valores para las facetas de precisión y escala al convertir a `Edm.Decimal`.</span><span class="sxs-lookup"><span data-stu-id="05441-121">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="05441-122">Si no se proporcionan explícitamente, los valores predeterminados para la precisión y la escala son 18 y 0, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="05441-122">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="05441-123">Concretamente, las sobrecargas siguientes son compatibles con `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="05441-123">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
- `CAST( d as Edm.Decimal );`  
  
- `CAST( d as Edm.Decimal(precision) );`  
  
- `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="05441-124">El uso de una expresión de conversión se considera una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="05441-124">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="05441-125">Las conversiones explícitas pueden truncar datos o perder precisión.</span><span class="sxs-lookup"><span data-stu-id="05441-125">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05441-126">CAST solo se admite en tipos primitivos y tipos de miembro de enumeración.</span><span class="sxs-lookup"><span data-stu-id="05441-126">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05441-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05441-127">Example</span></span>  

 <span data-ttu-id="05441-128">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador CAST para convertir una expresión de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="05441-128">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="05441-129">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="05441-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="05441-130">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="05441-130">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="05441-131">Siga el procedimiento descrito en [Cómo: ejecutar una consulta que devuelve resultados PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="05441-131">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="05441-132">Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="05441-132">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="05441-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="05441-133">See also</span></span>

- [<span data-ttu-id="05441-134">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="05441-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
