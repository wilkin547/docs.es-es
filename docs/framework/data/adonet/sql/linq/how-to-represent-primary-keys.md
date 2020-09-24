---
title: Procedimiento para representar claves principales
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 02570176c8aef5cfdc7ba09fd6976f430900e8df
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166240"
---
# <a name="how-to-represent-primary-keys"></a>Procedimiento para representar claves principales

Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar una propiedad o un campo que represente la clave principal de una columna de base de datos.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite las columnas calculadas como claves principales.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>Para designar una propiedad o un campo como clave principal  
  
1. Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Especifique el valor como `true`.  
  
## <a name="see-also"></a>Consulte también

- [El modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedimiento para personalizar clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
