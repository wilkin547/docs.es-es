---
title: Filtrar para representar columnas calculadas
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: f624bb49773af2c0053851ac55727b6db8632131
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204125"
---
# <a name="how-to-represent-computed-columns"></a>Filtrar para representar columnas calculadas
Use la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> propiedad en un <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para representar una columna cuyo contenido es el resultado del cálculo.  
  
 Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite columnas calculadas como claves principales.  
  
### <a name="to-represent-a-computed-column"></a>Para representar una columna calculada  
  
1.  Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
2.  Asigne una representación de cadena de la fórmula a la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
## <a name="see-also"></a>Vea también

- [El modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Filtrar para personalizar clases de entidades con el editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
