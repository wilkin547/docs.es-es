---
title: ISOF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: a0294f425552df3329d158d69a6d503b2f008780
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542338"
---
# <a name="isof-entity-sql"></a><span data-ttu-id="26145-102">ISOF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="26145-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="26145-103">Determina si el tipo de una expresión es del tipo especificado o uno de sus subtipos.</span><span class="sxs-lookup"><span data-stu-id="26145-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26145-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26145-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="26145-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="26145-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="26145-106">Cualquier expresión de consulta válida de la que se va a determinar el tipo.</span><span class="sxs-lookup"><span data-stu-id="26145-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="26145-107">NOT</span><span class="sxs-lookup"><span data-stu-id="26145-107">NOT</span></span>  
 <span data-ttu-id="26145-108">Niega el resultado EDM.Boolean de IS OF.</span><span class="sxs-lookup"><span data-stu-id="26145-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="26145-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="26145-109">ONLY</span></span>  
 <span data-ttu-id="26145-110">Especifica que IS OF devuelve `true` solo si `expression` es de tipo `type` y no de uno cualquiera de sus subtipos.</span><span class="sxs-lookup"><span data-stu-id="26145-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="26145-111">Tipo con el que se va a probar `expression`.</span><span class="sxs-lookup"><span data-stu-id="26145-111">The type to test `expression` against.</span></span> <span data-ttu-id="26145-112">El tipo debe estar calificado por el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="26145-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26145-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="26145-113">Return Value</span></span>  
 <span data-ttu-id="26145-114">`true` si `expression` es de tipo T y T es un tipo base o un tipo derivado de `type`; NULL si `expression` es nulo en tiempo de ejecución; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="26145-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26145-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26145-115">Remarks</span></span>  
 <span data-ttu-id="26145-116">Las expresiones `expression IS NOT OF (type)` y `expression IS NOT OF (ONLY type)` son sintácticamente equivalentes a `NOT (expression IS OF (type))` y `NOT (expression IS OF (ONLY type))` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="26145-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="26145-117">En la tabla siguiente se muestra el comportamiento del operador `IS OF` en algunos patrones de esquina típicos.</span><span class="sxs-lookup"><span data-stu-id="26145-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="26145-118">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="26145-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="26145-119">Patrón</span><span class="sxs-lookup"><span data-stu-id="26145-119">Pattern</span></span>|<span data-ttu-id="26145-120">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="26145-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="26145-121">null IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="26145-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="26145-122">Produce</span><span class="sxs-lookup"><span data-stu-id="26145-122">Throws</span></span>|  
|<span data-ttu-id="26145-123">null IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="26145-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="26145-124">Produce</span><span class="sxs-lookup"><span data-stu-id="26145-124">Throws</span></span>|  
|<span data-ttu-id="26145-125">null IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="26145-125">null IS OF (RowType)</span></span>|<span data-ttu-id="26145-126">Produce</span><span class="sxs-lookup"><span data-stu-id="26145-126">Throws</span></span>|  
|<span data-ttu-id="26145-127">TREAT (null AS EntityType) IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="26145-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="26145-128">Devuelve DBNull</span><span class="sxs-lookup"><span data-stu-id="26145-128">Returns DBNull</span></span>|  
|<span data-ttu-id="26145-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="26145-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="26145-130">Produce</span><span class="sxs-lookup"><span data-stu-id="26145-130">Throws</span></span>|  
|<span data-ttu-id="26145-131">TREAT (null AS RowType) IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="26145-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="26145-132">Produce</span><span class="sxs-lookup"><span data-stu-id="26145-132">Throws</span></span>|  
|<span data-ttu-id="26145-133">EntityType IS OF (EntityType)</span><span class="sxs-lookup"><span data-stu-id="26145-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="26145-134">Devuelve true o false</span><span class="sxs-lookup"><span data-stu-id="26145-134">Returns true/false</span></span>|  
|<span data-ttu-id="26145-135">ComplexType IS OF (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="26145-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="26145-136">Produce</span><span class="sxs-lookup"><span data-stu-id="26145-136">Throws</span></span>|  
|<span data-ttu-id="26145-137">RowType IS OF (RowType)</span><span class="sxs-lookup"><span data-stu-id="26145-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="26145-138">Produce</span><span class="sxs-lookup"><span data-stu-id="26145-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26145-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26145-139">Example</span></span>  
 <span data-ttu-id="26145-140">La consulta de siguiente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador is of para determinar el tipo de una expresión de consulta y, a continuación, usa el operador TREAT para convertir un objeto del tipo Course en una colección de objetos del tipo OnsiteCourse.</span><span class="sxs-lookup"><span data-stu-id="26145-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="26145-141">La consulta se basa en el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="26145-141">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 <span data-ttu-id="26145-142">[! code-SQL [DP EntityServices Concepts # TREAT_ISOF] ~/samples/Snippets/TSQL/VS_Snippets_Data/DP EntityServices Concepts/TSQL/EntitySql. SQL # treat_isof)]</span><span class="sxs-lookup"><span data-stu-id="26145-142">[!code-sql[DP EntityServices Concepts#TREAT_ISOF]~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26145-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="26145-143">See also</span></span>

- [<span data-ttu-id="26145-144">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="26145-144">Entity SQL Reference</span></span>](entity-sql-reference.md)
