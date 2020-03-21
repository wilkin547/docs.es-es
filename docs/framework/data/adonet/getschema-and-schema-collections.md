---
title: GetSchema y colecciones de esquema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: e18c23e9bbec97a64110aba6eb7241761ecece06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149562"
---
# <a name="getschema-and-schema-collections"></a>GetSchema y colecciones de esquema
Las clases **connection** de cada uno de los proveedores administrados de .NET Framework implementan un método **GetSchema** que se usa para recuperar <xref:System.Data.DataTable>información de esquema sobre la base de datos que está conectada actualmente y la información de esquema devuelta desde el método **GetSchema** viene en forma de archivo . El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se va a devolver y restringir la cantidad de información devuelta.  
  
## <a name="specifying-the-schema-collections"></a>Especificación de las colecciones de esquemas  
 El primer parámetro opcional del método **GetSchema** es el nombre de la colección que se especifica como una cadena. Existen dos tipos de colecciones de esquemas: comunes, que son comunes a todos los proveedores, y específicas, que son específicas de cada proveedor.  
  
 Puede consultar un proveedor administrado de .NET Framework para determinar la lista de colecciones de esquemas compatibles llamando al método **GetSchema** sin argumentos o con el nombre de colección de esquemas "MetaDataCollections". Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.  
  
### <a name="retrieving-schema-collections-example"></a>Ejemplo de recuperación de colecciones de esquemas  
 En los ejemplos siguientes <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> se muestra cómo utilizar el método <xref:System.Data.SqlClient.SqlConnection> del proveedor de datos de .NET Framework para la clase de SQL Server para recuperar información de esquema sobre todas las tablas contenidas en la base de datos de ejemplo **AdventureWorks:**  
  
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
  
## <a name="see-also"></a>Consulte también

- [Recuperación de información del esquema de la base de datos](retrieving-database-schema-information.md)
- [Información general de ADO.NET](ado-net-overview.md)
