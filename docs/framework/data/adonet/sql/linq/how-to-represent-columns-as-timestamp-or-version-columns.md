---
title: Procedimiento para representar columnas como columnas de marcas de tiempo o de versión
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: ef99e0420b328f94686e08256ecf229000467810
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793501"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>Procedimiento para representar columnas como columnas de marcas de tiempo o de versión
Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> propiedad del <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar que un campo o propiedad representa una columna de base de datos que contiene marcas de tiempo de base de datos o números de versión.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>Para designar que un campo o propiedad representa una columna de marca de tiempo o versión  
  
1. Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> en `true`.  
  
## <a name="see-also"></a>Vea también

- [Modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedimientos: Especificar los miembros para los que se van a probar los conflictos de simultaneidad](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [Cómo: Personalización de clases de entidad mediante el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
