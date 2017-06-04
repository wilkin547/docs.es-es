---
title: "Operaciones &#250;nicas de copia masiva | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Operaciones &#250;nicas de copia masiva
La manera más sencilla de realizar una operación de copia masiva de SQL Server es ejecutar una sola operación con respecto a una base de datos.  De forma predeterminada, las operaciones de copia masiva se realizan como una operación aislada: la operación de copia tiene lugar sin transacción, sin la oportunidad de revertirla.  
  
> [!NOTE]
>  Si necesita revertir la copia masiva total o parcialmente cuando se produce un error, puede utilizar una transacción administrada por <xref:System.Data.SqlClient.SqlBulkCopy> o realizar la operación de copia masiva en una transacción existente.  **SqlBulkCopy** también funciona con <xref:System.Transactions> si la conexión está inscrita \(implícita o explícitamente\) en una transacción **System.Transactions**.  
>   
>  Para obtener más información, consulta [Transacción y operaciones de copia masiva](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).  
  
 Los pasos generales para realizar una operación de copia masiva son los siguientes:  
  
1.  conéctese al servidor de origen y obtenga los datos que se van a copiar.  Los datos también pueden proceder de otros orígenes, si se pueden recuperar de un objeto <xref:System.Data.IDataReader> o <xref:System.Data.DataTable>.  
  
2.  Conéctese al servidor de destino \(a menos que desee que **SqlBulkCopy** establezca una conexión automáticamente\).  
  
3.  Cree un objeto <xref:System.Data.SqlClient.SqlBulkCopy> y configure las propiedades necesarias.  
  
4.  Establezca la propiedad **DestinationTableName** para indicar la tabla de destino de la operación de inserción masiva.  
  
5.  Llame a uno de los métodos **WriteToServer**.  
  
6.  Como opción, actualice las propiedades y llame de nuevo a **WriteToServer** si es necesario.  
  
7.  Llame a <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, o incluya las operaciones de copia masiva en una instrucción `Using`.  
  
> [!CAUTION]
>  Es recomendable que los tipos de datos de las columnas de origen y destino coincidan.  Si los tipos de datos no coinciden, **SqlBulkCopy** intenta convertir los valores de origen al tipo de datos de destino, mediante el uso de las reglas empleadas por <xref:System.Data.SqlClient.SqlParameter.Value%2A>.  Las conversiones pueden afectar al rendimiento y también dar lugar a errores inesperados.  Por ejemplo, un tipo de datos `Double` se puede convertir a un tipo de datos `Decimal` la mayoría de las veces, pero no siempre.  
  
## Ejemplo  
 En la siguiente aplicación de consola se demuestra cómo cargar datos mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.  En este ejemplo, se usa <xref:System.Data.SqlClient.SqlDataReader> para copiar datos de la tabla **Production.Product** ubicada en la base de datos **AdventureWorks** de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] a una tabla similar en la misma base de datos.  
  
> [!IMPORTANT]
>  Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en [Configuración de ejemplo de copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).  Este código se proporciona para mostrar cuál debe ser la sintaxis cuando solo se utiliza **SqlBulkCopy**.  Si las tablas de origen y de destino están incluidas en la misma instancia de SQL Server, lo más rápido y sencillo es usar una instrucción `INSERT … SELECT` de Transact\-SQL para copiar los datos.  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## Realización de una operación de copia masiva mediante Transact\-SQL y la clase Command  
 En el siguiente ejemplo se ilustra cómo utilizar el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> para ejecutar la instrucción BULK INSERT.  
  
> [!NOTE]
>  La ruta de acceso al archivo del origen de los datos es relativa al servidor.  El proceso de servidor debe tener acceso a ella para que la operación de copia masiva se realice correctamente.  
  
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
  
## Vea también  
 [Operaciones de copia masiva en SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)