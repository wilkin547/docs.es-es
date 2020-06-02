---
title: Procedimiento para insertar filas en la base de datos
description: Aprenda a insertar filas en una base de datos agregando LINQ to SQL objetos a una colección relacionada con la tabla. LINQ to SQL traduce adiciones a comandos INSERT de SQL.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: 39eee6edf59d2adb7de41efd88899050fbe69fd8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286357"
---
# <a name="how-to-insert-rows-into-the-database"></a>Procedimiento para insertar filas en la base de datos

Para insertar filas en una base de datos, se agregan objetos a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> colección asociada y, a continuación, se envían los cambios a la base de datos. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]convierte los cambios en los comandos SQL adecuados `INSERT` .

> [!NOTE]
> Puede invalidar los métodos predeterminados de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para las operaciones de base de datos `Insert`, `Update` y `Delete`. Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).
>
> Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con el mismo propósito.

En los pasos siguientes se asume que un objeto <xref:System.Data.Linq.DataContext> válido le conecta a la base de datos Northwind. Para obtener más información, consulte [Cómo: conectarse a una base de datos](how-to-connect-to-a-database.md).

### <a name="to-insert-a-row-into-the-database"></a>Para insertar una fila en la base de datos

1. Cree un nuevo objeto que incluya los datos de la columna que se van a enviar.

2. Agregue el nuevo objeto a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` colección asociada a la tabla de destino en la base de datos.

3. Envíe el cambio a la base de datos.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se crea un nuevo objeto de tipo `Order` y se llena con los valores adecuados. Después, se agrega el nuevo objeto a la colección `Order`. Finalmente, se envía el cambio a la base de datos, como una nueva fila de la tabla `Orders`.

[!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
[!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]

## <a name="see-also"></a>Consulte también

- [Procedimiento para administrar conflictos de cambios](how-to-manage-change-conflicts.md)
- [DataContext (métodos) (Object Relational Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [Cómo: Asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Realizar y enviar cambios de datos](making-and-submitting-data-changes.md)
