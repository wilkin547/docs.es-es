---
description: 'Más información acerca de: operaciones de copia masiva únicas'
title: Operaciones de copia masiva únicas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: f6b046fbd73ad798f3f9f117eea0b72f46e43b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767484"
---
# <a name="single-bulk-copy-operations"></a>Operaciones de copia masiva únicas

El método más sencillo para realizar una operación de copia masiva de SQL Server es realizar una operación única con una base de datos. De forma predeterminada, una operación de copia masiva se realiza como una operación aislada: la operación de copia tiene lugar sin transacciones y no es posible revertirla.

> [!NOTE]
> Si necesita revertir toda o parte de la copia masiva cuando se produce un error, puede usar una transacción administrada por <xref:System.Data.SqlClient.SqlBulkCopy> o realizar la operación de copia masiva en una transacción existente. **SqlBulkCopy** también funciona con <xref:System.Transactions> si la conexión está inscrita (implícita o explícitamente) en una transacción **System.Transactions**.
>
> Para obtener más información, vea [transacciones y operaciones de copia masiva](transaction-and-bulk-copy-operations.md).

Los pasos generales para realizar una operación de copia masiva son los siguientes:

1. Conéctese al servidor de origen y obtenga los datos que se van a copiar. Los datos también pueden provenir de otros orígenes, si se pueden recuperar de un objeto <xref:System.Data.IDataReader> o <xref:System.Data.DataTable>.

2. Conéctese al servidor de destino (a menos que quiera que **SqlBulkCopy** establezca una conexión automáticamente).

3. Cree un objeto de <xref:System.Data.SqlClient.SqlBulkCopy>, estableciendo las propiedades necesarias.

4. Establezca la propiedad **DestinationTableName** para indicar la tabla de destino de la operación de inserción masiva.

5. Llame a uno de los métodos **WriteToServer**.

6. Como opción, actualice las propiedades y llame de nuevo a **WriteToServer** si fuese necesario.

7. Llame a <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>o ajuste las operaciones de copia masiva dentro de una instrucción `Using`.

> [!CAUTION]
> Se recomienda que los tipos de datos de la columna de origen y de destino coincidan. Si los tipos de datos no coinciden, **SqlBulkCopy** intenta convertir los valores de origen en el tipo de datos de destino mediante las reglas empleadas por <xref:System.Data.SqlClient.SqlParameter.Value%2A>. Las conversiones pueden afectar al rendimiento y también pueden producir errores inesperados. Por ejemplo, un tipo de datos `Double` puede convertirse en un tipo de datos `Decimal` la mayoría de las veces, pero no siempre.

## <a name="example"></a>Ejemplo

La aplicación de consola siguiente muestra cómo cargar datos mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>. En este ejemplo se usa <xref:System.Data.SqlClient.SqlDataReader> para copiar datos de la tabla **Production.Product** de la base de datos **AdventureWorks** de SQL Server en una tabla similar de la misma base de datos.

> [!IMPORTANT]
> Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en el ejemplo de configuración de la [copia masiva](bulk-copy-example-setup.md). Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy**. Si las tablas de origen y destino se encuentran en la misma instancia de SQL Server, es más fácil y rápido usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.

[!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
[!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]

## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a>Realización de una operación de copia masiva mediante Transact-SQL y la clase Command

En el ejemplo siguiente se muestra cómo usar el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> para ejecutar la instrucción BULK INSERT.

> [!NOTE]
> La ruta de acceso al origen de datos depende del servidor. El proceso del servidor debe tener acceso a esa ruta para que la operación de copia masiva se realice correctamente.

```vb
Using connection As SqlConnection = New SqlConnection(connectionString)
Dim queryString As String = _
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"
connection.Open()
SqlCommand command = New SqlCommand(queryString, connection);

command.ExecuteNonQuery()
End Using
```

```csharp
using (SqlConnection connection = New SqlConnection(connectionString))
{
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +
    "FROM 'f:\mydata\data.tbl' " +
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";
connection.Open();
SqlCommand command = new SqlCommand(queryString, connection);

command.ExecuteNonQuery();
}
```

## <a name="see-also"></a>Vea también

- [Operaciones de copia masiva en SQL Server](bulk-copy-operations-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
