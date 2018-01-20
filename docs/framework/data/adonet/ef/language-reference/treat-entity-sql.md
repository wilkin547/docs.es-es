---
title: TREAT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 248ea49bd66300e0cf000bee4861b9556ff081bb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="treat-entity-sql"></a><span data-ttu-id="d20b9-102">TREAT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d20b9-102">TREAT (Entity SQL)</span></span>
<span data-ttu-id="d20b9-103">Trata un objeto de un tipo base determinado como un objeto del tipo derivado especificado.</span><span class="sxs-lookup"><span data-stu-id="d20b9-103">Treats an object of a particular base type as an object of the specified derived type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d20b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d20b9-104">Syntax</span></span>  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a><span data-ttu-id="d20b9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d20b9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d20b9-106">Cualquier expresión de consulta válida que devuelve una entidad.</span><span class="sxs-lookup"><span data-stu-id="d20b9-106">Any valid query expression that returns an entity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d20b9-107">El tipo de la expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo del tipo de expresión.</span><span class="sxs-lookup"><span data-stu-id="d20b9-107">The type of the specified expression must be a subtype of the specified data type, or the data type must be a subtype of the type of expression.</span></span>  
  
 `type`  
 <span data-ttu-id="d20b9-108">Tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="d20b9-108">An entity type.</span></span> <span data-ttu-id="d20b9-109">El tipo debe estar calificado por un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d20b9-109">The type must be qualified by a namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d20b9-110">La expresión especificada debe ser un subtipo del tipo de datos especificado, o el tipo de datos debe ser un subtipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="d20b9-110">The specified expression must be a subtype of the specified data type, or the data type must be a subtype of the expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d20b9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d20b9-111">Return Value</span></span>  
 <span data-ttu-id="d20b9-112">Un valor del tipo de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="d20b9-112">A value of the specified data type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d20b9-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d20b9-113">Remarks</span></span>  
 <span data-ttu-id="d20b9-114">TREAT se utiliza para realizar una conversión entre clases relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d20b9-114">TREAT is used to perform upcasting between related classes.</span></span> <span data-ttu-id="d20b9-115">Por ejemplo, si `Employee` deriva de `Person` y p es de tipo `Person`, `TREAT(p AS NamespaceName.Employee)` convierte una instancia de `Person` genérica a `Employee`; es decir, permite tratar p como `Employee`.</span><span class="sxs-lookup"><span data-stu-id="d20b9-115">For example, if `Employee` derives from `Person` and p is of type `Person`, `TREAT(p AS NamespaceName.Employee)` upcasts a generic `Person` instance to `Employee`; that is, it allows you to treat p as `Employee`.</span></span>  
  
 <span data-ttu-id="d20b9-116">TREAT se utiliza en situaciones de herencia donde se puede realizar una consulta como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d20b9-116">TREAT is used in inheritance scenarios where you can do a query like the following:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 <span data-ttu-id="d20b9-117">Este consulta convierte entidades `Person` al tipo `Employee` .</span><span class="sxs-lookup"><span data-stu-id="d20b9-117">This query upcasts `Person` entities to the `Employee` type.</span></span> <span data-ttu-id="d20b9-118">Si el valor de p no es realmente de tipo `Employee`, la expresión obtiene el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="d20b9-118">If the value of p is not actually of type `Employee`, the expression yields the value `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d20b9-119">La expresión especificada `Employee` debe ser un subtipo del tipo de datos especificado `Person`, o el tipo de datos debe ser un subtipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="d20b9-119">The specified expression `Employee` must be a subtype of the specified data type `Person`, or the data type must be a subtype of the expression.</span></span> <span data-ttu-id="d20b9-120">De lo contrario, la expresión producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d20b9-120">Otherwise, the expression will result in a compile-time error.</span></span>  
  
 <span data-ttu-id="d20b9-121">En la tabla siguiente se muestra el comportamiento del tratamiento en algunos patrones típicos y algunos patrones menos comunes.</span><span class="sxs-lookup"><span data-stu-id="d20b9-121">The following table shows the behavior of treat over some typical patterns and some less common patterns.</span></span> <span data-ttu-id="d20b9-122">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="d20b9-122">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="d20b9-123">Modelo</span><span class="sxs-lookup"><span data-stu-id="d20b9-123">Pattern</span></span>|<span data-ttu-id="d20b9-124">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="d20b9-124">Behavior</span></span>|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|<span data-ttu-id="d20b9-125">Devuelve `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="d20b9-125">Returns `DbNull`.</span></span>|  
|`TREAT (null AS ComplexType)`|<span data-ttu-id="d20b9-126">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="d20b9-126">Throws an exception.</span></span>|  
|`TREAT (null AS RowType)`|<span data-ttu-id="d20b9-127">Produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="d20b9-127">Throws an exception/</span></span>|  
|`TREAT (EntityType AS EntityType)`|<span data-ttu-id="d20b9-128">Devuelve `EntityType` o `null`.</span><span class="sxs-lookup"><span data-stu-id="d20b9-128">Returns `EntityType` or `null`.</span></span>|  
|`TREAT (ComplexType AS ComplexType)`|<span data-ttu-id="d20b9-129">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="d20b9-129">Throws an exception.</span></span>|  
|`TREAT (RowType AS RowType)`|<span data-ttu-id="d20b9-130">Inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="d20b9-130">Throws an exception.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d20b9-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d20b9-131">Example</span></span>  
 <span data-ttu-id="d20b9-132">La consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] siguiente usa el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="d20b9-132">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="d20b9-133">La consulta se basa en el [modelo School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span><span class="sxs-lookup"><span data-stu-id="d20b9-133">The query is based on the [School Model](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="d20b9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d20b9-134">See Also</span></span>  
 [<span data-ttu-id="d20b9-135">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d20b9-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="d20b9-136">Tipos estructurados que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="d20b9-136">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
