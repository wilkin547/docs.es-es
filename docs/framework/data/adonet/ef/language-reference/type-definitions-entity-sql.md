---
title: Definiciones de tipo (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b890a56daeab1c3a0fbb8c95ec29a81cb7689e9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="64916-102">Definiciones de tipo (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="64916-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="64916-103">Las definiciones de tipo se usan en la instrucción de declaración de una función inline de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64916-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64916-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64916-104">Remarks</span></span>  
 <span data-ttu-id="64916-105">La instrucción de declaración para una función inline consta de los [función](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) palabra clave seguido por el identificador que representa el nombre de función (por ejemplo, "MyAvg") seguido por una lista de definiciones de parámetro entre paréntesis (para ejemplo, "cuota Collection(Decimal)").</span><span class="sxs-lookup"><span data-stu-id="64916-105">The declaration statement for an inline function consists of the [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="64916-106">La lista de definición de parámetros está formada por cero o más definiciones de parámetro.</span><span class="sxs-lookup"><span data-stu-id="64916-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="64916-107">Cada definición de parámetro consta de un identificador (el nombre del parámetro proporcionado a la función, por ejemplo, "cuota") seguido de una definición de tipo (por ejemplo, "Collection(Decimal)").</span><span class="sxs-lookup"><span data-stu-id="64916-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="64916-108">Las definiciones de tipo pueden ser:</span><span class="sxs-lookup"><span data-stu-id="64916-108">The type definitions can be either:</span></span>  
  
-   <span data-ttu-id="64916-109">El tipo del identificador (por ejemplo, "Int32" o "AdventureWorks.Order").</span><span class="sxs-lookup"><span data-stu-id="64916-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
-   <span data-ttu-id="64916-110">La palabra clave `COLLECTION` seguida de otra definición de tipo entre paréntesis (por ejemplo, "Collection(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="64916-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
-   <span data-ttu-id="64916-111">La palabra clave ROW seguida de una lista de definiciones de propiedad entre paréntesis (por ejemplo, "Row(x AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="64916-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="64916-112">Las definiciones de propiedad tienen un formato como "`identifier type_definition`, `identifier type_definition`,...".</span><span class="sxs-lookup"><span data-stu-id="64916-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
-   <span data-ttu-id="64916-113">La palabra clave REF seguida del tipo del identificador entre paréntesis (por ejemplo, "Ref(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="64916-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="64916-114">El operador de definición de tipo REF requiere un tipo de entidad como argumento.</span><span class="sxs-lookup"><span data-stu-id="64916-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="64916-115">No puede especificar un tipo primitivo como argumento.</span><span class="sxs-lookup"><span data-stu-id="64916-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="64916-116">También puede anidar las definiciones de tipo (por ejemplo, "Collection(Row(x Ref(AdventureWorks.Order)))").</span><span class="sxs-lookup"><span data-stu-id="64916-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="64916-117">Las opciones de definiciones de tipo son:</span><span class="sxs-lookup"><span data-stu-id="64916-117">The type definition options are:</span></span>  
  
-   <span data-ttu-id="64916-118">`IdentifierName supported_type` o</span><span class="sxs-lookup"><span data-stu-id="64916-118">`IdentifierName supported_type`, or</span></span>  
  
-   <span data-ttu-id="64916-119">`IdentifierName` COLLECTION(`type_definition`) o</span><span class="sxs-lookup"><span data-stu-id="64916-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
-   <span data-ttu-id="64916-120">`IdentifierName` ROW(`property_definition`) o</span><span class="sxs-lookup"><span data-stu-id="64916-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
-   <span data-ttu-id="64916-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="64916-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="64916-122">La opción de definición de propiedad es `IdentifierName type_definition`.</span><span class="sxs-lookup"><span data-stu-id="64916-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="64916-123">Los tipos admitidos son los del espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="64916-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="64916-124">Entre ellos se incluyen los tipos primitivos y de entidad.</span><span class="sxs-lookup"><span data-stu-id="64916-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="64916-125">Los tipos de entidad admitidos solo hacen referencia a tipos de entidad del espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="64916-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="64916-126">Entre ellos no se incluyen los tipos primitivos.</span><span class="sxs-lookup"><span data-stu-id="64916-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="64916-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="64916-127">Examples</span></span>  
 <span data-ttu-id="64916-128">A continuación se muestra un ejemplo de una definición de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="64916-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="64916-129">A continuación se muestra un ejemplo de una definición de tipo COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="64916-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="64916-130">A continuación se muestra un ejemplo de una definición de tipo ROW.</span><span class="sxs-lookup"><span data-stu-id="64916-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="64916-131">A continuación se muestra un ejemplo de una definición de tipo REF.</span><span class="sxs-lookup"><span data-stu-id="64916-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="64916-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="64916-132">See Also</span></span>  
 [<span data-ttu-id="64916-133">Información general sobre de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="64916-133">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="64916-134">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="64916-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
