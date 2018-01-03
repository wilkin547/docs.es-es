---
title: GetSchema y colecciones de esquema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d982964b596528b091f5367edd38e0cee5f923c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getschema-and-schema-collections"></a>GetSchema y colecciones de esquema
El **conexión** clases en cada uno de lo proveedores administrados de .NET Framework implementan un **GetSchema** método que se usa para recuperar información de esquema de la base de datos que está conectado actualmente, y la información de esquema devuelta desde el **GetSchema** método viene en forma de un <xref:System.Data.DataTable>. El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas para devolver y para restringir la cantidad de información devuelta.  
  
## <a name="specifying-the-schema-collections"></a>Especificación de las colecciones de esquemas  
 El primer parámetro opcional de la **GetSchema** método es el nombre de la colección que se especifica como una cadena. Existen dos tipos de colecciones de esquemas: comunes, que son comunes a todos los proveedores, y específicas, que son específicas de cada proveedor.  
  
 Puede consultar un proveedor administrado de .NET Framework para determinar la lista de colecciones de esquemas admitidas mediante la llamada la **GetSchema** método sin argumentos o con el nombre de la colección de esquemas "MetaDataCollections". Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.  
  
### <a name="retrieving-schema-collections-example"></a>Ejemplo de recuperación de colecciones de esquemas  
 Los ejemplos siguientes muestran cómo utilizar el <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> método del proveedor de datos de .NET Framework para SQL Server <xref:System.Data.SqlClient.SqlConnection> clase para recuperar información de esquema de todas las tablas contenidas en el **AdventureWorks**base de datos de ejemplo:  
  
```vb  
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
  
```csharp  
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
  
## <a name="see-also"></a>Vea también  
 [Recuperación de información del esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
