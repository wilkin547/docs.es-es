---
title: Procedimiento para representar tablas como clases
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: c02922351909b097dc06085eefbcc0f131350505
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166227"
---
# <a name="how-to-represent-tables-as-classes"></a>Procedimiento para representar tablas como clases

Utilice el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atributo para designar una clase como una clase de entidad asociada a una tabla de base de datos.  
  
### <a name="to-map-a-class-to-a-database-table"></a>Para asignar una clase a una tabla de base de datos  
  
- Agregue el atributo <xref:System.Data.Linq.Mapping.TableAttribute> a la declaración de la clase.  
  
## <a name="example"></a>Ejemplo  

 El código siguiente establece la clase `Customer` como una clase de entidad que está asociada a la tabla de base de datos `Customers`.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> si se puede deducir el nombre. Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.  
  
## <a name="see-also"></a>Consulte también

- [El modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedimiento para personalizar clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
