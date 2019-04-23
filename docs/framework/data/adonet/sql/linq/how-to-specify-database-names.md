---
title: Procedimiento para especificar nombres de base de datos
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: a43a7ac541adb984eeb8bb88b7ab96db86baf26c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335282"
---
# <a name="how-to-specify-database-names"></a>Procedimiento para especificar nombres de base de datos
Utilice la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en un atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> para especificar el nombre de una base de datos cuando la conexión no proporciona ninguno.  
  
 Para consultar muestras de código, vea <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### <a name="to-specify-the-name-of-the-database"></a>Para especificar el nombre de la base de datos  
  
1. Agregue el atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> a la declaración de clase para la base de datos.  
  
2. Agregue la propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> al atributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
3. Establezca el valor de propiedad <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> en el nombre que desea especificar.  
  
## <a name="see-also"></a>Vea también

- [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Cómo: Personalizar las clases de entidad mediante el Editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
