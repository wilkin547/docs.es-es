---
title: Procedimiento para actualizar filas en la base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: 2819cd5d2533e8e289735c3df2b39df952968e66
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938734"
---
# <a name="how-to-update-rows-in-the-database"></a>Procedimiento para actualizar filas en la base de datos
Puede actualizar las filas de una base de datos modificando los valores de miembro de los objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asociados a la <xref:System.Data.Linq.Table%601> colección y, a continuación, enviando los cambios a la base de datos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]convierte los cambios en los comandos SQL `UPDATE` adecuados.  
  
> [!NOTE]
> Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`. Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.  
  
 En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind. Para obtener más información, consulte [Cómo Conectarse a una base](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md)de datos.  
  
### <a name="to-update-a-row-in-the-database"></a>Para actualizar una fila de la base de datos  
  
1. Consulte en la base de datos la fila que se va a actualizar.  
  
2. Realice los cambios deseados en los valores de miembro en el objeto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] resultante.  
  
3. Envíe los cambios a la base de datos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta en la base de datos el pedido #11000 y, a continuación, se cambian los valores de `ShipName` y `ShipVia` en el objeto `Order` resultante. Finalmente, los cambios en estos valores de miembro se envían a la base de datos como cambios en las columnas `ShipName` y `ShipVia`.  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Realización y envío de cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
