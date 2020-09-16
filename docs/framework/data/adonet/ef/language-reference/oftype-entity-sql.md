---
title: OFTYPE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
ms.openlocfilehash: 375fe9ce52ae290c175e42276b6b526766f6699c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547517"
---
# <a name="oftype-entity-sql"></a><span data-ttu-id="9a536-102">OFTYPE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9a536-102">OFTYPE (Entity SQL)</span></span>
<span data-ttu-id="9a536-103">Devuelve una colección de objetos de una expresión de consulta de un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="9a536-103">Returns a collection of objects from a query expression that is of a specific type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a536-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a536-104">Syntax</span></span>  
  
```sql  
OFTYPE ( expression, [ONLY] test_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="9a536-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9a536-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9a536-106">Expresión de consulta válida que devuelve una colección de objetos.</span><span class="sxs-lookup"><span data-stu-id="9a536-106">Any valid query expression that returns a collection of objects.</span></span>  
  
 `test_type`  
 <span data-ttu-id="9a536-107">Tipo con el que probar cada objeto que devuelve `expression` .</span><span class="sxs-lookup"><span data-stu-id="9a536-107">The type to test each object returned by `expression` against.</span></span> <span data-ttu-id="9a536-108">El tipo debe estar calificado por un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="9a536-108">The type must be qualified by a namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a536-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a536-109">Return Value</span></span>  
 <span data-ttu-id="9a536-110">Colección de objetos que son del tipo `test_type`o de un tipo base o derivado de `test_type`.</span><span class="sxs-lookup"><span data-stu-id="9a536-110">A collection of objects that are of type `test_type`, or a base type or derived type of `test_type`.</span></span> <span data-ttu-id="9a536-111">Si se especifica ONLY, solo se devolverán las instancias de `test_type` o una colección vacía.</span><span class="sxs-lookup"><span data-stu-id="9a536-111">If ONLY is specified, only instances of the `test_type` or an empty collection will be returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a536-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a536-112">Remarks</span></span>  
 <span data-ttu-id="9a536-113">Una expresión `OFTYPE` especifica una expresión de un tipo que se emite para realizar una prueba del tipo con cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="9a536-113">An `OFTYPE` expression specifies a type expression that is issued to perform a type test against each element of a collection.</span></span>  <span data-ttu-id="9a536-114">La expresión `OFTYPE` produce una nueva colección del tipo especificado que contiene solo los elementos que eran equivalentes a ese tipo o a alguno de sus subtipos.</span><span class="sxs-lookup"><span data-stu-id="9a536-114">The `OFTYPE` expression produces a new collection of the specified type containing only those elements that were either equivalent to that type or a sub-type of it.</span></span>  
  
 <span data-ttu-id="9a536-115">Una expresión `OFTYPE` es una abreviatura de la expresión de consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a536-115">An `OFTYPE` expression is an abbreviation of the following query expression:</span></span>  
  
```sql  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 <span data-ttu-id="9a536-116">Dado que Manager es un subtipo de Employee, la expresión siguiente produce una colección de jefes (managers) únicamente a partir de una colección de empleados (employees):</span><span class="sxs-lookup"><span data-stu-id="9a536-116">Given that a Manager is a subtype of Employee, the following expression produces a collection of only managers from a collection of employees:</span></span>  
  
```sql  
OfType(employees, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="9a536-117">También es posible convertir una colección utilizando el filtro de tipo:</span><span class="sxs-lookup"><span data-stu-id="9a536-117">It is also possible to up cast a collection using the type filter:</span></span>  
  
```sql
OfType(executives, NamespaceName.Manager)  
```  
  
 <span data-ttu-id="9a536-118">Puesto que todos los ejecutivos (executive) son jefes (managers), la colección resultante todavía contiene a todos los ejecutivos originales, aunque ahora tengan el tipo de una colección de administradores.</span><span class="sxs-lookup"><span data-stu-id="9a536-118">Since all executives are managers, the resulting collection still contains all the original executives, though the collection is now typed as a collection of managers.</span></span>  
  
 <span data-ttu-id="9a536-119">En la tabla siguiente se muestra el comportamiento del operador `OFTYPE` en algunos patrones.</span><span class="sxs-lookup"><span data-stu-id="9a536-119">The following table shows the behavior of the `OFTYPE` operator over some patterns.</span></span> <span data-ttu-id="9a536-120">Todas las excepciones se producen en el cliente antes de que se llame al proveedor:</span><span class="sxs-lookup"><span data-stu-id="9a536-120">All exceptions are thrown from the client side before the provider is invoked:</span></span>  
  
|<span data-ttu-id="9a536-121">Patrón</span><span class="sxs-lookup"><span data-stu-id="9a536-121">Pattern</span></span>|<span data-ttu-id="9a536-122">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="9a536-122">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="9a536-123">OFTYPE(Collection(EntityType), EntityType)</span><span class="sxs-lookup"><span data-stu-id="9a536-123">OFTYPE(Collection(EntityType), EntityType)</span></span>|<span data-ttu-id="9a536-124">Collection(EntityType)</span><span class="sxs-lookup"><span data-stu-id="9a536-124">Collection(EntityType)</span></span>|  
|<span data-ttu-id="9a536-125">OFTYPE(Collection(ComplexType), ComplexType)</span><span class="sxs-lookup"><span data-stu-id="9a536-125">OFTYPE(Collection(ComplexType), ComplexType)</span></span>|<span data-ttu-id="9a536-126">Produce</span><span class="sxs-lookup"><span data-stu-id="9a536-126">Throws</span></span>|  
|<span data-ttu-id="9a536-127">OFTYPE(Collection(RowType), RowType)</span><span class="sxs-lookup"><span data-stu-id="9a536-127">OFTYPE(Collection(RowType), RowType)</span></span>|<span data-ttu-id="9a536-128">Produce</span><span class="sxs-lookup"><span data-stu-id="9a536-128">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9a536-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a536-129">Example</span></span>  
 <span data-ttu-id="9a536-130">La siguiente consulta de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usa el operador OFTYPE para devolver una colección de objetos OnsiteCourse a partir de una colección de objetos Course.</span><span class="sxs-lookup"><span data-stu-id="9a536-130">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the OFTYPE operator to return a collection of OnsiteCourse objects from a collection of Course objects.</span></span> <span data-ttu-id="9a536-131">La consulta se basa en el [modelo School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9a536-131">The query is based on the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OFTYPE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#oftype)]  
  
## <a name="see-also"></a><span data-ttu-id="9a536-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a536-132">See also</span></span>

- [<span data-ttu-id="9a536-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9a536-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
