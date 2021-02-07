---
description: 'Más información sobre: Cómo: representar columnas como permitir valores NULL'
title: Procedimiento para representar columnas como columnas que permiten valores null
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 019affd13fa9c2629c6a0ec66c42f19842a4d824
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695910"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>Procedimiento para representar columnas como columnas que permiten valores null

Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para especificar que la columna de base de datos asociada puede contener valores NULL.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>Para designar que una columna permite valores nulos  
  
1. Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2. Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> en `true`.  
  
## <a name="see-also"></a>Vea también

- [El modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedimiento para personalizar clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
