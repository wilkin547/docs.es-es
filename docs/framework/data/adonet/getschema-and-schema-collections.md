---
title: "GetSchema y colecciones de esquemas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# GetSchema y colecciones de esquemas
Las clases **Connection** de cada uno de los proveedores administrados de .NET Framework implementan un método **GetSchema** que se utiliza para recuperar información de esquema de la base de datos que está actualmente conectada. La información de esquema que devuelve el método **GetSchema** viene en forma de una <xref:System.Data.DataTable>.  El método **GetSchema** es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se devolverá y para restringir la cantidad de información devuelta.  
  
## Especificación de las colecciones de esquemas  
 El primer parámetro opcional del método **GetSchema** es el nombre de la colección que se especifica como una cadena.  Existen dos tipos de colecciones de esquemas: comunes, que son comunes a todos los proveedores, y específicas, que son específicas de cada proveedor.  
  
 Puede consultar un proveedor administrado de .NET Framework para determinar la lista de colecciones de esquemas admitidas mediante la llamada al método **GetSchema** sin argumentos, o con el nombre de colección de esquemas "MetaDataCollections".  Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.  
  
### Ejemplo de recuperación de colecciones de esquemas  
 En los siguientes ejemplos se muestra cómo utilizar el método <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> del proveedor de datos .NET Framework para la clase <xref:System.Data.SqlClient.SqlConnection> de SQL Server para recuperar información de esquema de todas las tablas contenidas en la base de datos de ejemplo **AdventureWorks**:  
  
 \[Visual Basic\]  
  
```  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
 \[C\#\]  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## Vea también  
 [Recuperar información de esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)