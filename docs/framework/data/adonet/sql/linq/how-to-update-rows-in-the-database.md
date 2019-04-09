---
title: Filtrar para actualizar filas en la base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: 84ef85b1e53d97ff468c3360af5e394a0e4ad776
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091205"
---
# <a name="how-to-update-rows-in-the-database"></a>Filtrar para actualizar filas en la base de datos
Puede actualizar las filas de una base de datos mediante la modificación de valores de miembros de los objetos asociados con el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> colección y, a continuación, enviar los cambios a la base de datos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Convierte los cambios en el código SQL apropiado `UPDATE` comandos.  
  
> [!NOTE]
>  Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`. Para obtener más información, consulte [personalizar Insert, Update y las operaciones de eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Los desarrolladores que usan Visual Studio pueden usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para desarrollar procedimientos almacenados para el mismo propósito.  
  
 En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind. Para obtener más información, vea [Cómo: Conectarse a una base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### <a name="to-update-a-row-in-the-database"></a>Para actualizar una fila de la base de datos  
  
1.  Consulte en la base de datos la fila que se va a actualizar.  
  
2.  Realice los cambios deseados en los valores de miembro en el objeto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] resultante.  
  
3.  Envíe los cambios a la base de datos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta en la base de datos el pedido #11000 y, a continuación, se cambian los valores de `ShipName` y `ShipVia` en el objeto `Order` resultante. Finalmente, los cambios en estos valores de miembro se envían a la base de datos como cambios en las columnas `ShipName` y `ShipVia`.  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Filtrar para administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Filtrar Asignación de procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Realizar y enviar cambios de datos](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
