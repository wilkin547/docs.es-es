---
title: Procedimiento para representar columnas como columnas de marcas de tiempo o de versión
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: cc8538ab7b2ecf5183cfb97995c04648493a369f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191754"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>Procedimiento para representar columnas como columnas de marcas de tiempo o de versión

Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> propiedad del <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar que un campo o propiedad representa una columna de base de datos que contiene marcas de tiempo de base de datos o números de versión.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>Para designar que un campo o propiedad representa una columna de marca de tiempo o versión  
  
1. Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> en `true`.  
  
## <a name="see-also"></a>Consulte también

- [El modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedimiento para especificar en qué miembros se comprueban los conflictos de simultaneidad](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [Procedimiento para personalizar clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
