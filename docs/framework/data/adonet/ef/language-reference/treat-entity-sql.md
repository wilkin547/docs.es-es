---
description: 'Más información sobre: TREAT (Entity SQL)'
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 3f014cac631d246b35d145cdb80c9aa6ac401524
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673432"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="64bc0-103">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="64bc0-103">TREAT (Entity SQL)</span></span>

<span data-ttu-id="64bc0-104">Trata un objeto de un tipo base determinado como un objeto del tipo derivado especificado.</span><span class="sxs-lookup"><span data-stu-id="64bc0-104">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64bc0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64bc0-105">Syntax</span></span>  
  
```sql  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="64bc0-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="64bc0-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="64bc0-107">Cualquier expresión de consulta válida que devuelve una entidad.</span><span class="sxs-lookup"><span data-stu-id="64bc0-107">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64bc0-108">El tipo de la expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo del tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="64bc0-108">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="64bc0-109">Tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="64bc0-109">An entity type.</span></span> <span data-ttu-id="64bc0-110">El tipo debe estar calificado por un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="64bc0-110">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64bc0-111">La expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="64bc0-111">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64bc0-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64bc0-112">Return Value</span></span>  

 <span data-ttu-id="64bc0-113">Un valor del tipo de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="64bc0-113">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64bc0-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="64bc0-114">Remarks</span></span>  

 <span data-ttu-id="64bc0-115">TREAT se utiliza para realizar una conversión entre clases relacionadas.</span><span class="sxs-lookup"><span data-stu-id="64bc0-115">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="64bc0-116">Por ejemplo, si `Employee` deriva de `Person` y p es de tipo `Person`, `TREAT(p AS NamespaceName.Employee)` convierte una instancia de `Person` genérica a `Employee`; es decir, permite tratar p como `Employee`.</span><span class="sxs-lookup"><span data-stu-id="64bc0-116">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="64bc0-117">TREAT se utiliza en situaciones de herencia donde se puede realizar una consulta como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="64bc0-117">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)
```  
  
 <span data-ttu-id="64bc0-118">Este consulta convierte entidades `Person` al tipo `Employee` .</span><span class="sxs-lookup"><span data-stu-id="64bc0-118">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="64bc0-119">Si el valor de p no es realmente de tipo `Employee`, la expresión obtiene el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="64bc0-119">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64bc0-120">La expresión especificada `Employee` debe ser un subtipo del tipo de datos especificado `Person` , o el tipo de datos debe ser un subtipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="64bc0-120">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="64bc0-121">De lo contrario, la expresión producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="64bc0-121">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="64bc0-122">En la tabla siguiente se muestra el comportamiento del tratamiento en algunos patrones típicos y algunos patrones menos comunes.</span><span class="sxs-lookup"><span data-stu-id="64bc0-122">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="64bc0-123">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="64bc0-123">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="64bc0-124">Patrón</span><span class="sxs-lookup"><span data-stu-id="64bc0-124">Pattern</span></span>|<span data-ttu-id="64bc0-125">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="64bc0-125">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="64bc0-126">Devuelve `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="64bc0-126">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="64bc0-127">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="64bc0-127">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="64bc0-128">Produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="64bc0-128">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="64bc0-129">Devuelve `EntityType` o `null`.</span><span class="sxs-lookup"><span data-stu-id="64bc0-129">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="64bc0-130">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="64bc0-130">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="64bc0-131">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="64bc0-131">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="64bc0-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64bc0-132">Example</span></span>  

 <span data-ttu-id="64bc0-133">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="64bc0-133">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="64bc0-134">La consulta se basa en el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="64bc0-134">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-sql[DP EntityServices Concepts#TREAT_ISOF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="64bc0-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="64bc0-135">See also</span></span>

- [<span data-ttu-id="64bc0-136">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="64bc0-136">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="64bc0-137">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="64bc0-137">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
