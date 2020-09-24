---
title: Procedimiento para representar columnas como miembros de clase
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: e73b017b5a500a8c48b3fe22557f6c6619f3b227
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166357"
---
# <a name="how-to-represent-columns-as-class-members"></a>Procedimiento para representar columnas como miembros de clase

Utilice el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para asociar un campo o una propiedad a una columna de base de datos.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>Para asignar un campo o una propiedad a una columna de base de datos  
  
- Agregue el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> a la propiedad o declaración de campo.  
  
## <a name="example"></a>Ejemplo  

 El código siguiente asigna el campo `CustomerID` de la clase `Customer` a la columna `CustomerID` de la tabla de base de datos `Customers`.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 No tiene que especificar la propiedad <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> si se puede deducir el nombre. Si no especifica ningún nombre, se supone que es el mismo que el de la propiedad o campo.  
  
## <a name="see-also"></a>Consulte también

- [El modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedimiento para personalizar clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
