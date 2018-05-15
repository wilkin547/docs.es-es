---
title: GetSchema y colecciones de esquema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: 1694a6de515e5326264f345f50d0730fe2a62e4f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="290e3-102">GetSchema y colecciones de esquema</span><span class="sxs-lookup"><span data-stu-id="290e3-102">GetSchema and Schema Collections</span></span>
<span data-ttu-id="290e3-103">El **conexión** clases en cada uno de lo proveedores administrados de .NET Framework implementan un **GetSchema** método que se usa para recuperar información de esquema de la base de datos que está conectado actualmente, y la información de esquema devuelta desde el **GetSchema** método viene en forma de un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="290e3-103">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="290e3-104">El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas para devolver y para restringir la cantidad de información devuelta.</span><span class="sxs-lookup"><span data-stu-id="290e3-104">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="290e3-105">Especificación de las colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="290e3-105">Specifying the Schema Collections</span></span>  
 <span data-ttu-id="290e3-106">El primer parámetro opcional de la **GetSchema** método es el nombre de la colección que se especifica como una cadena.</span><span class="sxs-lookup"><span data-stu-id="290e3-106">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="290e3-107">Existen dos tipos de colecciones de esquemas: comunes, que son comunes a todos los proveedores, y específicas, que son específicas de cada proveedor.</span><span class="sxs-lookup"><span data-stu-id="290e3-107">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="290e3-108">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de colecciones de esquemas admitidas mediante la llamada la **GetSchema** método sin argumentos o con el nombre de la colección de esquemas "MetaDataCollections".</span><span class="sxs-lookup"><span data-stu-id="290e3-108">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="290e3-109">Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.</span><span class="sxs-lookup"><span data-stu-id="290e3-109">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="290e3-110">Ejemplo de recuperación de colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="290e3-110">Retrieving Schema Collections Example</span></span>  
 <span data-ttu-id="290e3-111">Los ejemplos siguientes muestran cómo utilizar el <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> método del proveedor de datos de .NET Framework para SQL Server <xref:System.Data.SqlClient.SqlConnection> clase para recuperar información de esquema de todas las tablas contenidas en el **AdventureWorks**base de datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="290e3-111">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="290e3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="290e3-112">See Also</span></span>  
 [<span data-ttu-id="290e3-113">Recuperación de información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="290e3-113">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="290e3-114">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="290e3-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
