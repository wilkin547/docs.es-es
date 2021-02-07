---
description: 'Más información acerca de: ISOF (Entity SQL)'
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 4a44ddc74ef16ec16285132f6567ca2500e173a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748354"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="bcbc2-103">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-103">ISOF (Entity SQL)</span></span>

<span data-ttu-id="bcbc2-104">Determina si el tipo de una expresión es del tipo especificado o uno de sus subtipos.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-104">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcbc2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcbc2-105">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="bcbc2-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bcbc2-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="bcbc2-107">Cualquier expresión de consulta válida de la que se va a determinar el tipo.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-107">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="bcbc2-108">NOT</span><span class="sxs-lookup"><span data-stu-id="bcbc2-108">NOT</span></span>  
 <span data-ttu-id="bcbc2-109">Niega el resultado EDM.Boolean de IS OF.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-109">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="bcbc2-110">ONLY</span><span class="sxs-lookup"><span data-stu-id="bcbc2-110">ONLY</span></span>  
 <span data-ttu-id="bcbc2-111">Especifica que IS OF devuelve `true` solo si `expression` es de tipo `type` y no de uno cualquiera de sus subtipos.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-111">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="bcbc2-112">Tipo con el que se va a probar `expression`.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-112">The type to test `expression` against.</span></span> <span data-ttu-id="bcbc2-113">El tipo debe estar calificado por el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-113">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcbc2-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bcbc2-114">Return Value</span></span>  

 <span data-ttu-id="bcbc2-115">`true` si `expression` es de tipo T y T es un tipo base o un tipo derivado de `type`; NULL si `expression` es nulo en tiempo de ejecución; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-115">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcbc2-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bcbc2-116">Remarks</span></span>  

 <span data-ttu-id="bcbc2-117">Las expresiones `expression IS NOT OF (type)` y `expression IS NOT OF (ONLY type)` son sintácticamente equivalentes a `NOT (expression IS OF (type))` y `NOT (expression IS OF (ONLY type))` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-117">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="bcbc2-118">En la tabla siguiente se muestra el comportamiento del operador `IS OF` en algunos patrones de esquina típicos.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-118">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="bcbc2-119">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="bcbc2-119">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="bcbc2-120">Patrón</span><span class="sxs-lookup"><span data-stu-id="bcbc2-120">Pattern</span></span>|<span data-ttu-id="bcbc2-121">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="bcbc2-121">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="bcbc2-122">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-122">null IS OF (EntityType)</span></span>|<span data-ttu-id="bcbc2-123">Produce</span><span class="sxs-lookup"><span data-stu-id="bcbc2-123">Throws</span></span>|  
|<span data-ttu-id="bcbc2-124">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-124">null IS OF (ComplexType)</span></span>|<span data-ttu-id="bcbc2-125">Produce</span><span class="sxs-lookup"><span data-stu-id="bcbc2-125">Throws</span></span>|  
|<span data-ttu-id="bcbc2-126">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-126">null IS OF (RowType)</span></span>|<span data-ttu-id="bcbc2-127">Produce</span><span class="sxs-lookup"><span data-stu-id="bcbc2-127">Throws</span></span>|  
|<span data-ttu-id="bcbc2-128">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-128">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="bcbc2-129">Devuelve DBNull</span><span class="sxs-lookup"><span data-stu-id="bcbc2-129">Returns DBNull</span></span>|  
|<span data-ttu-id="bcbc2-130">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-130">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="bcbc2-131">Produce</span><span class="sxs-lookup"><span data-stu-id="bcbc2-131">Throws</span></span>|  
|<span data-ttu-id="bcbc2-132">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-132">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="bcbc2-133">Produce</span><span class="sxs-lookup"><span data-stu-id="bcbc2-133">Throws</span></span>|  
|<span data-ttu-id="bcbc2-134">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-134">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="bcbc2-135">Devuelve true o false</span><span class="sxs-lookup"><span data-stu-id="bcbc2-135">Returns true/false</span></span>|  
|<span data-ttu-id="bcbc2-136">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-136">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="bcbc2-137">Produce</span><span class="sxs-lookup"><span data-stu-id="bcbc2-137">Throws</span></span>|  
|<span data-ttu-id="bcbc2-138">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="bcbc2-138">RowType IS OF (RowType)</span></span>|<span data-ttu-id="bcbc2-139">Produce</span><span class="sxs-lookup"><span data-stu-id="bcbc2-139">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bcbc2-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bcbc2-140">Example</span></span>  

 <span data-ttu-id="bcbc2-141">La consulta de siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador is of para determinar el tipo de una expresión de consulta y, a continuación, usa el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="bcbc2-141">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="bcbc2-142">La consulta se basa en el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bcbc2-142">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 <span data-ttu-id="bcbc2-143">[! code-SQL [DP EntityServices Concepts # TREAT_ISOF] ~/samples/Snippets/TSQL/VS_Snippets_Data/DP EntityServices Concepts/TSQL/EntitySql. SQL # treat_isof)]</span><span class="sxs-lookup"><span data-stu-id="bcbc2-143">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbc2-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcbc2-144">See also</span></span>

- [<span data-ttu-id="bcbc2-145">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="bcbc2-145">Entity SQL Reference</span></span>](entity-sql-reference.md)
