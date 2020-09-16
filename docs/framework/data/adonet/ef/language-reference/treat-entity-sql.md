---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 566ac875aec17e4d0aa22ec1962053aeb6ae2a2e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558854"
---
# <a name="treat-entity-sql"></a><span data-ttu-id="44621-102">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="44621-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="44621-103">Trata un objeto de un tipo base determinado como un objeto del tipo derivado especificado.</span><span class="sxs-lookup"><span data-stu-id="44621-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44621-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44621-104">Syntax</span></span>  
  
```sql  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="44621-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="44621-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="44621-106">Cualquier expresión de consulta válida que devuelve una entidad.</span><span class="sxs-lookup"><span data-stu-id="44621-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44621-107">El tipo de la expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo del tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="44621-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="44621-108">Tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="44621-108">An entity type.</span></span> <span data-ttu-id="44621-109">El tipo debe estar calificado por un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="44621-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44621-110">La expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="44621-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44621-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="44621-111">Return Value</span></span>  
 <span data-ttu-id="44621-112">Un valor del tipo de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="44621-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44621-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44621-113">Remarks</span></span>  
 <span data-ttu-id="44621-114">TREAT se utiliza para realizar una conversión entre clases relacionadas.</span><span class="sxs-lookup"><span data-stu-id="44621-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="44621-115">Por ejemplo, si `Employee` deriva de `Person` y p es de tipo `Person`, `TREAT(p AS NamespaceName.Employee)` convierte una instancia de `Person` genérica a `Employee`; es decir, permite tratar p como `Employee`.</span><span class="sxs-lookup"><span data-stu-id="44621-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="44621-116">TREAT se utiliza en situaciones de herencia donde se puede realizar una consulta como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="44621-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)
```  
  
 <span data-ttu-id="44621-117">Este consulta convierte entidades `Person` al tipo `Employee` .</span><span class="sxs-lookup"><span data-stu-id="44621-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="44621-118">Si el valor de p no es realmente de tipo `Employee`, la expresión obtiene el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="44621-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44621-119">La expresión especificada `Employee` debe ser un subtipo del tipo de datos especificado `Person` , o el tipo de datos debe ser un subtipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="44621-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="44621-120">De lo contrario, la expresión producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="44621-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="44621-121">En la tabla siguiente se muestra el comportamiento del tratamiento en algunos patrones típicos y algunos patrones menos comunes.</span><span class="sxs-lookup"><span data-stu-id="44621-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="44621-122">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="44621-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="44621-123">Patrón</span><span class="sxs-lookup"><span data-stu-id="44621-123">Pattern</span></span>|<span data-ttu-id="44621-124">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="44621-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="44621-125">Devuelve `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="44621-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="44621-126">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="44621-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="44621-127">Produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="44621-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="44621-128">Devuelve `EntityType` o `null`.</span><span class="sxs-lookup"><span data-stu-id="44621-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="44621-129">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="44621-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="44621-130">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="44621-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="44621-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44621-131">Example</span></span>  
 <span data-ttu-id="44621-132">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="44621-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="44621-133">La consulta se basa en el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="44621-133">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-sql[DP EntityServices Concepts#TREAT_ISOF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="44621-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="44621-134">See also</span></span>

- [<span data-ttu-id="44621-135">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="44621-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="44621-136">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="44621-136">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
