---
description: 'Más información acerca de: GetSchema y colecciones de esquemas'
title: GetSchema y colecciones de esquema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: 2b085435f0f9ea9ec33897ee417cd7a726c4503d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723990"
---
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="54177-103">GetSchema y colecciones de esquema</span><span class="sxs-lookup"><span data-stu-id="54177-103">GetSchema and Schema Collections</span></span>

<span data-ttu-id="54177-104">Las clases de **conexión** de cada uno de los proveedores administrados de .NET Framework implementan un método **GetSchema** que se utiliza para recuperar información de esquema sobre la base de datos que está conectada actualmente, y la información de esquema devuelta desde el método **GetSchema** tiene el formato de <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="54177-104">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="54177-105">El método **GetSchema** es un método sobrecargado que proporciona parámetros opcionales para especificar la colección de esquemas que se devolverá y restringe la cantidad de información devuelta.</span><span class="sxs-lookup"><span data-stu-id="54177-105">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="54177-106">Especificación de las colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="54177-106">Specifying the Schema Collections</span></span>  

 <span data-ttu-id="54177-107">El primer parámetro opcional del método **GetSchema** es el nombre de la colección que se especifica como una cadena.</span><span class="sxs-lookup"><span data-stu-id="54177-107">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="54177-108">Existen dos tipos de colecciones de esquemas: comunes, que son comunes a todos los proveedores, y específicas, que son específicas de cada proveedor.</span><span class="sxs-lookup"><span data-stu-id="54177-108">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="54177-109">Puede consultar un proveedor administrado de .NET Framework para determinar la lista de colecciones de esquemas admitidas llamando al método **GetSchema** sin argumentos o con el nombre de la colección de esquemas "MetaDataCollections".</span><span class="sxs-lookup"><span data-stu-id="54177-109">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="54177-110">Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.</span><span class="sxs-lookup"><span data-stu-id="54177-110">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="54177-111">Ejemplo de recuperación de colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="54177-111">Retrieving Schema Collections Example</span></span>  

 <span data-ttu-id="54177-112">En los siguientes ejemplos se muestra cómo utilizar el <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> método del proveedor de datos .NET Framework para la <xref:System.Data.SqlClient.SqlConnection> clase SQL Server para recuperar información de esquema de todas las tablas contenidas en la base de datos de ejemplo **AdventureWorks** :</span><span class="sxs-lookup"><span data-stu-id="54177-112">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54177-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54177-113">See also</span></span>

- [<span data-ttu-id="54177-114">Recuperación de la información del esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="54177-114">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="54177-115">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="54177-115">ADO.NET Overview</span></span>](ado-net-overview.md)
