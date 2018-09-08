---
title: Operaciones de copia masiva únicas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: 274a6e87b272002a567fd92605c4e690c03b6e26
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190207"
---
# <a name="single-bulk-copy-operations"></a>Operaciones de copia masiva únicas
La manera más sencilla de realizar una operación de copia masiva de SQL Server es ejecutar una sola operación con respecto a una base de datos. De forma predeterminada, las operaciones de copia masiva se realizan como una operación aislada: la operación de copia tiene lugar sin transacción, sin la oportunidad de revertirla.  
  
> [!NOTE]
>  Si necesita revertir la copia masiva total o parcialmente cuando se produce un error, puede utilizar una transacción administrada por <xref:System.Data.SqlClient.SqlBulkCopy> o realizar la operación de copia masiva en una transacción existente. **SqlBulkCopy** también funcionará con <xref:System.Transactions> si la conexión está inscrita (implícita o explícitamente) en un **System.Transactions** transacciones.  
>   
>  Para obtener más información, consulte [transacciones y operaciones de copia masiva](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).  
  
 Los pasos generales para realizar una operación de copia masiva son los siguientes:  
  
1.  conéctese al servidor de origen y obtenga los datos que se van a copiar. Los datos también pueden proceder de otros orígenes, si se pueden recuperar de un objeto <xref:System.Data.IDataReader> o <xref:System.Data.DataTable>.  
  
2.  Conectarse al servidor de destino (a menos que desee **SqlBulkCopy** para establecer una conexión automáticamente).  
  
3.  Cree un objeto <xref:System.Data.SqlClient.SqlBulkCopy> y configure las propiedades necesarias.  
  
4.  Establecer el **DestinationTableName** propiedad para indicar la tabla de destino para la masiva de la operación de inserción.  
  
5.  Llame a uno de los **WriteToServer** métodos.  
  
6.  Opcionalmente, actualice las propiedades y llame **WriteToServer** nuevo según sea necesario.  
  
7.  Llame a <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, o incluya las operaciones de copia masiva en una instrucción `Using`.  
  
> [!CAUTION]
>  Es recomendable que los tipos de datos de las columnas de origen y destino coincidan. Si no coinciden los tipos de datos, **SqlBulkCopy** intenta convertir cada valor de origen en el tipo de datos de destino, utilizando las reglas empleadas por <xref:System.Data.SqlClient.SqlParameter.Value%2A>. Las conversiones pueden afectar al rendimiento y también dar lugar a errores inesperados. Por ejemplo, un tipo de datos `Double` se puede convertir a un tipo de datos `Decimal` la mayoría de las veces, pero no siempre.  
  
## <a name="example"></a>Ejemplo  
 En la siguiente aplicación de consola se demuestra cómo cargar datos mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>. En este ejemplo, un <xref:System.Data.SqlClient.SqlDataReader> se usa para copiar datos desde el **Production.Product** tabla en SQL Server**AdventureWorks** base de datos a una tabla similar en la misma base de datos.  
  
> [!IMPORTANT]
>  En este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en [configuración de ejemplo de copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy** solo. Si las tablas de origen y de destino están incluidas en la misma instancia de SQL Server, lo más rápido y sencillo es usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a>Realización de una operación de copia masiva mediante Transact-SQL y la clase Command  
 En el siguiente ejemplo se ilustra cómo utilizar el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> para ejecutar la instrucción BULK INSERT.  
  
> [!NOTE]
>  La ruta de acceso al archivo del origen de los datos es relativa al servidor. El proceso de servidor debe tener acceso a ella para que la operación de copia masiva se realice correctamente.  
  
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
 [Operaciones de copia masiva en SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
