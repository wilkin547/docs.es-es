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
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="a1b63-102">GetSchema y colecciones de esquema</span><span class="sxs-lookup"><span data-stu-id="a1b63-102">GetSchema and Schema Collections</span></span>
<span data-ttu-id="a1b63-103">Las clases **connection** de cada uno de los proveedores administrados de .NET Framework implementan un método **GetSchema** que se usa para recuperar <xref:System.Data.DataTable>información de esquema sobre la base de datos que está conectada actualmente y la información de esquema devuelta desde el método **GetSchema** viene en forma de archivo .</span><span class="sxs-lookup"><span data-stu-id="a1b63-103">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="a1b63-104">El **GetSchema** método es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se va a devolver y restringir la cantidad de información devuelta.</span><span class="sxs-lookup"><span data-stu-id="a1b63-104">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="a1b63-105">Especificación de las colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="a1b63-105">Specifying the Schema Collections</span></span>  
 <span data-ttu-id="a1b63-106">El primer parámetro opcional del método **GetSchema** es el nombre de la colección que se especifica como una cadena.</span><span class="sxs-lookup"><span data-stu-id="a1b63-106">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="a1b63-107">Existen dos tipos de colecciones de esquemas: comunes, que son comunes a todos los proveedores, y específicas, que son específicas de cada proveedor.</span><span class="sxs-lookup"><span data-stu-id="a1b63-107">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="a1b63-108">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de colecciones de esquemas compatibles llamando al método **GetSchema** sin argumentos o con el nombre de colección de esquemas "MetaDataCollections".</span><span class="sxs-lookup"><span data-stu-id="a1b63-108">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="a1b63-109">Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.</span><span class="sxs-lookup"><span data-stu-id="a1b63-109">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="a1b63-110">Ejemplo de recuperación de colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="a1b63-110">Retrieving Schema Collections Example</span></span>  
 <span data-ttu-id="a1b63-111">En los ejemplos siguientes <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> se muestra cómo utilizar el método <xref:System.Data.SqlClient.SqlConnection> del proveedor de datos de .NET Framework para la clase de SQL Server para recuperar información de esquema sobre todas las tablas contenidas en la base de datos de ejemplo **AdventureWorks:**</span><span class="sxs-lookup"><span data-stu-id="a1b63-111">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1b63-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1b63-112">See also</span></span>

- [<span data-ttu-id="a1b63-113">Recuperación de información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="a1b63-113">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="a1b63-114">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1b63-114">ADO.NET Overview</span></span>](ado-net-overview.md)
