---
title: "Modificar datos con procedimientos almacenados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Modificar datos con procedimientos almacenados
Los procedimientos almacenados pueden aceptar datos como parámetros de entrada y pueden devolver datos como parámetros de salida, conjuntos de resultados o valores de retorno.  En el ejemplo siguiente se muestra cómo ADO.NET envía y recibe parámetros de entrada, parámetros de salida y valores de retorno.  El ejemplo inserta un nuevo registro en una tabla cuya columna de clave principal es una columna de identidad en una base de datos de SQL Server.  
  
> [!NOTE]
>  Si está utilizando procedimientos almacenados de SQL Server para editar o eliminar datos con <xref:System.Data.SqlClient.SqlDataAdapter>, asegúrese de que no utiliza SET NOCOUNT ON en la definición del procedimiento almacenado.  Esto hace que el recuento de filas afectadas vuelva a cero, lo que `DataAdapter` interpreta como un conflicto de simultaneidad.  En este caso, se iniciará una <xref:System.Data.DBConcurrencyException>.  
  
## Ejemplo  
 En el ejemplo se utiliza el siguiente procedimiento almacenado para insertar una nueva categoría en la tabla **Categories** de **Northwind**.  El procedimiento almacenado recibe el valor de la columna **CategoryName** como parámetro de entrada y usa la función SCOPE\_IDENTITY\(\) para recuperar el nuevo valor del campo de identidad, **CategoryID**, y devolverlo en un parámetro de salida.  La instrucción RETURN utiliza la función @@ROWCOUNT para devolver el número de filas insertadas.  
  
```  
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 En el siguiente ejemplo de código se utiliza el anterior procedimiento almacenado `InsertCategory` como origen de la propiedad <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> de <xref:System.Data.SqlClient.SqlDataAdapter>.  El parámetro de salida `@Identity` se reflejará en <xref:System.Data.DataSet> una vez que se haya insertado el registro en la base de dados al llamar al método `Update` del <xref:System.Data.SqlClient.SqlDataAdapter>.  El código también recupera el valor devuelto.  
  
> [!NOTE]
>  En el caso de <xref:System.Data.OleDb.OleDbDataAdapter>, los parámetros con un <xref:System.Data.ParameterDirection> con el valor **ReturnValue** se deben especificar antes que los restantes parámetros.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## Vea también  
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [DataAdapters y DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Ejecutar un comando](../../../../docs/framework/data/adonet/executing-a-command.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)