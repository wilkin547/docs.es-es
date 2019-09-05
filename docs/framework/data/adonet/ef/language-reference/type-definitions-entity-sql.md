---
title: Definiciones de tipo (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 471964266c290d5eba95804dbe1c2bc5225e3f83
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248949"
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="80420-102">Definiciones de tipo (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="80420-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="80420-103">Las definiciones de tipo se usan en la instrucción de declaración de una función inline de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80420-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80420-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80420-104">Remarks</span></span>  
 <span data-ttu-id="80420-105">La instrucción de declaración de una función insertada se compone de la palabra clave [function](function-entity-sql.md) seguida del identificador que representa el nombre de función (por ejemplo, "MiFuncion") seguido de una lista de definiciones de parámetros entre paréntesis (por ejemplo, "colección de tasas ()". Decimal) ").</span><span class="sxs-lookup"><span data-stu-id="80420-105">The declaration statement for an inline function consists of the [FUNCTION](function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="80420-106">La lista de definición de parámetros está formada por cero o más definiciones de parámetro.</span><span class="sxs-lookup"><span data-stu-id="80420-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="80420-107">Cada definición de parámetro consta de un identificador (el nombre del parámetro proporcionado a la función, por ejemplo, "cuota") seguido de una definición de tipo (por ejemplo, "Collection(Decimal)").</span><span class="sxs-lookup"><span data-stu-id="80420-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="80420-108">Las definiciones de tipo pueden ser:</span><span class="sxs-lookup"><span data-stu-id="80420-108">The type definitions can be either:</span></span>  
  
- <span data-ttu-id="80420-109">El tipo del identificador (por ejemplo, "Int32" o "AdventureWorks.Order").</span><span class="sxs-lookup"><span data-stu-id="80420-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
- <span data-ttu-id="80420-110">La palabra clave `COLLECTION` seguida de otra definición de tipo entre paréntesis (por ejemplo, "Collection(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="80420-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
- <span data-ttu-id="80420-111">La palabra clave ROW seguida de una lista de definiciones de propiedad entre paréntesis (por ejemplo, "Row(x AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="80420-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="80420-112">Las definiciones de propiedad tienen un formato como`identifier type_definition`" `identifier type_definition`,,...".</span><span class="sxs-lookup"><span data-stu-id="80420-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
- <span data-ttu-id="80420-113">La palabra clave REF seguida del tipo del identificador entre paréntesis (por ejemplo, "Ref(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="80420-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="80420-114">El operador de definición de tipo REF requiere un tipo de entidad como argumento.</span><span class="sxs-lookup"><span data-stu-id="80420-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="80420-115">No puede especificar un tipo primitivo como argumento.</span><span class="sxs-lookup"><span data-stu-id="80420-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="80420-116">También puede anidar las definiciones de tipo (por ejemplo, "Collection(Row(x Ref(AdventureWorks.Order)))").</span><span class="sxs-lookup"><span data-stu-id="80420-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="80420-117">Las opciones de definiciones de tipo son:</span><span class="sxs-lookup"><span data-stu-id="80420-117">The type definition options are:</span></span>  
  
- <span data-ttu-id="80420-118">`IdentifierName supported_type`, o</span><span class="sxs-lookup"><span data-stu-id="80420-118">`IdentifierName supported_type`, or</span></span>  
  
- <span data-ttu-id="80420-119">`IdentifierName` COLLECTION(`type_definition`) o</span><span class="sxs-lookup"><span data-stu-id="80420-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
- <span data-ttu-id="80420-120">`IdentifierName` ROW(`property_definition`) o</span><span class="sxs-lookup"><span data-stu-id="80420-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
- <span data-ttu-id="80420-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="80420-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="80420-122">La opción de definición de propiedad es `IdentifierName type_definition`.</span><span class="sxs-lookup"><span data-stu-id="80420-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="80420-123">Los tipos admitidos son los del espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="80420-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="80420-124">Entre ellos se incluyen los tipos primitivos y de entidad.</span><span class="sxs-lookup"><span data-stu-id="80420-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="80420-125">Los tipos de entidad admitidos solo hacen referencia a tipos de entidad del espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="80420-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="80420-126">Entre ellos no se incluyen los tipos primitivos.</span><span class="sxs-lookup"><span data-stu-id="80420-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="80420-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="80420-127">Examples</span></span>  
 <span data-ttu-id="80420-128">A continuación se muestra un ejemplo de una definición de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="80420-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="80420-129">A continuación se muestra un ejemplo de una definición de tipo COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="80420-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="80420-130">A continuación se muestra un ejemplo de una definición de tipo ROW.</span><span class="sxs-lookup"><span data-stu-id="80420-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="80420-131">A continuación se muestra un ejemplo de una definición de tipo REF.</span><span class="sxs-lookup"><span data-stu-id="80420-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="80420-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="80420-132">See also</span></span>

- [<span data-ttu-id="80420-133">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="80420-133">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="80420-134">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="80420-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
