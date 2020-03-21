---
title: Sistema de tipos (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: b8b721aff5b7886fdb897ecaa3dcc163ec94ae79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149836"
---
# <a name="type-system-entity-sql"></a>Sistema de tipos (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]admite varios tipos:  
  
- Tipos primitivos (simples), como `Int32` y `String.`.  
  
- Tipos nominales que se definen en el esquema, como <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> y <xref:System.Data.Metadata.Edm.RelationshipType>.  
  
- Tipos anónimos que no se definen explícitamente en el esquema: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> y <xref:System.Data.Metadata.Edm.RefType>.  
  
 En esta sección se describen los tipos anónimos que no están definidos en el esquema explícitamente pero que son compatibles con Entity SQLEntity SQL. Para obtener información sobre los tipos primitivos y nominales, vea Tipos de [modelo conceptual (CSDL).](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)  
  
## <a name="rows"></a>Filas  
 La estructura de una fila depende de la secuencia de miembros con nombre y con tipo de que consta la misma. Un tipo de fila no tiene ninguna identidad y no se puede heredar. Las instancias del mismo tipo de fila son equivalentes si los miembros son respectivamente equivalentes. Las filas no tienen ningún otro comportamiento más allá de su equivalencia estructural y no tienen ningún equivalente en Common Language Runtime. Las consultas pueden producir estructuras que contienen filas o colecciones de filas. El enlace de API entre las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y el lenguaje del host define el modo en que las filas se materializan en la consulta que generó el resultado. Para obtener información sobre cómo construir una instancia de fila, vea [Construir tipos](constructing-types-entity-sql.md).  
  
## <a name="collections"></a>Colecciones  
 Los tipos de colección representan cero o más instancias de otros objetos. Para obtener información sobre cómo construir una colección, vea [Construir tipos](constructing-types-entity-sql.md).  
  
## <a name="references"></a>Referencias  
 Una referencia es un puntero lógico a una entidad concreta en un conjunto de entidades específico.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite los operadores siguientes para construir, anular la construcción y navegar a través de referencias.  
  
- [Ref](ref-entity-sql.md)  
  
- [CREATEREF](createref-entity-sql.md)  
  
- [Clave](key-entity-sql.md)  
  
- [DEREF](deref-entity-sql.md)  
  
 Puede navegar por una referencia utilizando el operador de acceso a miembros (`.`) (punto). El fragmento de código siguiente extrae la propiedad Id (de Order) navegando por la propiedad r (referencia).  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 Si el valor de referencia es NULL o si el destino de la referencia no existe, el resultado es NULL.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Referencia de Entity SQL](entity-sql-reference.md)
- [Fundido](cast-entity-sql.md)
- [Especificaciones CSDL, SSDL MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
