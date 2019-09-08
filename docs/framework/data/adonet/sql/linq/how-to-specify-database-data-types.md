---
title: Procedimiento para especificar tipos de datos de base de datos
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 09ca8dc6fa440138523bcd2905335a04517dd806
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793274"
---
# <a name="how-to-specify-database-data-types"></a>Procedimiento para especificar tipos de datos de base de datos
Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar el texto exacto que define la columna en una declaración de tabla de T-SQL.  
  
 Debe especificar la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> sólo si piensa utilizar <xref:System.Data.Linq.DataContext.CreateDatabase%2A> para crear una instancia de la base de datos.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>Para especificar texto para definir un tipo de datos en una tabla T-SQL  
  
1. Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Establezca el valor de la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> en el texto exacto que T-SQL utiliza.  
  
## <a name="see-also"></a>Vea también

- [Modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Cómo: Personalización de clases de entidad mediante el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
