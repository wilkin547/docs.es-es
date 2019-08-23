---
title: Procedimiento para insertar filas en la base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 2852b0593f8b213f8cad6f9a2ab8f08eeb2a4dec
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943633"
---
# <a name="how-to-insert-rows-into-the-database"></a>Procedimiento para insertar filas en la base de datos
Para insertar filas en una base de datos, se agregan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objetos a la colección asociada <xref:System.Data.Linq.Table%601> y, a continuación, se envían los cambios a la base de datos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]convierte los cambios en los comandos SQL `INSERT` adecuados.  
  
> [!NOTE]
> Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`. Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.  
  
 En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind. Para obtener más información, vea [Cómo: Conectarse a una base](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)de datos.  
  
### <a name="to-insert-a-row-into-the-database"></a>Para insertar una fila en la base de datos  
  
1. Cree un nuevo objeto que incluya los datos de la columna que se van a enviar.  
  
2. Agregue el nuevo objeto a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` colección asociada a la tabla de destino en la base de datos.  
  
3. Envíe el cambio a la base de datos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se crea un nuevo objeto de tipo `Order` y se llena con los valores adecuados. Después, se agrega el nuevo objeto a la colección `Order`. Finalmente, se envía el cambio a la base de datos, como una nueva fila de la tabla `Orders`.  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Métodos DataContext (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Realización y envío de cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
