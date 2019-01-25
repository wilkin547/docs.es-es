---
title: Definiciones de tipo (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
ms.openlocfilehash: 7ac27c3dd43cb83272bff991dbd713e8269ccbb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743535"
---
# <a name="type-definitions-entity-sql"></a>Definiciones de tipo (Entity SQL)
Las definiciones de tipo se usan en la instrucción de declaración de una función inline de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="remarks"></a>Comentarios  
 La instrucción de declaración para una función inline consta de los [función](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) palabra clave seguido por el identificador que representa el nombre de función (por ejemplo, "MiFuncion") seguido por una lista de definiciones de parámetro entre paréntesis (para ejemplo, "cuota Collection.  
  
 La lista de definición de parámetros está formada por cero o más definiciones de parámetro. Cada definición de parámetro consta de un identificador (el nombre del parámetro proporcionado a la función, por ejemplo, "cuota") seguido de una definición de tipo (por ejemplo, "Collection(Decimal)").  
  
 Las definiciones de tipo pueden ser:  
  
-   El tipo del identificador (por ejemplo, "Int32" o "AdventureWorks.Order").  
  
-   La palabra clave `COLLECTION` seguida de otra definición de tipo entre paréntesis (por ejemplo, "Collection(AdventureWorks.Order)").  
  
-   La palabra clave ROW seguida de una lista de definiciones de propiedad entre paréntesis (por ejemplo, "Row(x AdventureWorks.Order)"). Definiciones de propiedad tienen un formato como "`identifier type_definition`, `identifier type_definition`,...".  
  
-   La palabra clave REF seguida del tipo del identificador entre paréntesis (por ejemplo, "Ref(AdventureWorks.Order)"). El operador de definición de tipo REF requiere un tipo de entidad como argumento. No puede especificar un tipo primitivo como argumento.  
  
 También puede anidar las definiciones de tipo (por ejemplo, "Collection(Row(x Ref(AdventureWorks.Order)))").  
  
 Las opciones de definiciones de tipo son:  
  
-   `IdentifierName supported_type` o  
  
-   `IdentifierName` COLLECTION(`type_definition`) o  
  
-   `IdentifierName` ROW(`property_definition`) o  
  
-   `IdentifierName` REF(`supported_entity_type`)  
  
 La opción de definición de propiedad es `IdentifierName type_definition`.  
  
 Los tipos admitidos son los del espacio de nombres actual. Entre ellos se incluyen los tipos primitivos y de entidad.  
  
 Los tipos de entidad admitidos solo hacen referencia a tipos de entidad del espacio de nombres actual. Entre ellos no se incluyen los tipos primitivos.  
  
## <a name="examples"></a>Ejemplos  
 A continuación se muestra un ejemplo de una definición de tipo simple.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 A continuación se muestra un ejemplo de una definición de tipo COLLECTION.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 A continuación se muestra un ejemplo de una definición de tipo ROW.  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 A continuación se muestra un ejemplo de una definición de tipo REF.  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a>Vea también
- [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
