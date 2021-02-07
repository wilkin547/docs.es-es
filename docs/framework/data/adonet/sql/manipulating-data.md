---
description: Más información acerca de cómo manipular datos
title: Manipular datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 51096a2e-8b38-4c4d-a523-799bfdb7ec69
ms.openlocfilehash: dba948fe923e709f6564e6c64fd9adce7f3f15f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767692"
---
# <a name="manipulating-data"></a><span data-ttu-id="90569-103">Manipular datos</span><span class="sxs-lookup"><span data-stu-id="90569-103">Manipulating Data</span></span>

<span data-ttu-id="90569-104">Antes de la introducción de conjuntos de resultados activos múltiples (MARS), los desarrolladores tenían que usar varias conexiones o cursores del lado servidor para resolver determinados escenarios.</span><span class="sxs-lookup"><span data-stu-id="90569-104">Before the introduction of Multiple Active Result Sets (MARS), developers had to use either multiple connections or server-side cursors to solve certain scenarios.</span></span> <span data-ttu-id="90569-105">Además, al usar varias conexiones en una situación transaccional, se necesitaban conexiones enlazadas (con **sp_getbindtoken** y **sp_bindsession**).</span><span class="sxs-lookup"><span data-stu-id="90569-105">In addition, when multiple connections were used in a transactional situation, bound connections (with **sp_getbindtoken** and **sp_bindsession**) were required.</span></span> <span data-ttu-id="90569-106">En los siguientes escenarios se muestra cómo usar una conexión habilitada para MARS en lugar de varias conexiones.</span><span class="sxs-lookup"><span data-stu-id="90569-106">The following scenarios show how to use a MARS-enabled connection instead of multiple connections.</span></span>  
  
## <a name="using-multiple-commands-with-mars"></a><span data-ttu-id="90569-107">Uso de varias comandos con MARS</span><span class="sxs-lookup"><span data-stu-id="90569-107">Using Multiple Commands with MARS</span></span>  

 <span data-ttu-id="90569-108">La siguiente aplicación de consola muestra cómo usar dos objetos <xref:System.Data.SqlClient.SqlDataReader> con dos objetos <xref:System.Data.SqlClient.SqlCommand> y un único objeto <xref:System.Data.SqlClient.SqlConnection> con MARS habilitado.</span><span class="sxs-lookup"><span data-stu-id="90569-108">The following Console application demonstrates how to use two <xref:System.Data.SqlClient.SqlDataReader> objects with two <xref:System.Data.SqlClient.SqlCommand> objects and a single <xref:System.Data.SqlClient.SqlConnection> object with MARS enabled.</span></span>  
  
### <a name="example"></a><span data-ttu-id="90569-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90569-109">Example</span></span>  

 <span data-ttu-id="90569-110">En el ejemplo se abre una única conexión a la base de datos **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="90569-110">The example opens a single connection to the **AdventureWorks** database.</span></span> <span data-ttu-id="90569-111">Con un objeto <xref:System.Data.SqlClient.SqlCommand>, se crea <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="90569-111">Using a <xref:System.Data.SqlClient.SqlCommand> object, a <xref:System.Data.SqlClient.SqlDataReader> is created.</span></span> <span data-ttu-id="90569-112">Cuando se utiliza el lector, se abre un segundo <xref:System.Data.SqlClient.SqlDataReader>, utilizando los datos del primer <xref:System.Data.SqlClient.SqlDataReader> como entrada de la cláusula WHERE para el segundo lector.</span><span class="sxs-lookup"><span data-stu-id="90569-112">As the reader is used, a second <xref:System.Data.SqlClient.SqlDataReader> is opened, using data from the first <xref:System.Data.SqlClient.SqlDataReader> as input to the WHERE clause for the second reader.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90569-113">En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="90569-113">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="90569-114">La cadena de conexión proporcionada en el código de ejemplo da por sentado que la base de datos está instalada y disponible en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="90569-114">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="90569-115">Modifique la cadena de conexión según sea necesario para el entorno.</span><span class="sxs-lookup"><span data-stu-id="90569-115">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
Option Explicit On  
  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
Module Module1  
  Sub Main()  
    ' By default, MARS is disabled when connecting  
    ' to a MARS-enabled host.  
    ' It must be enabled in the connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    Dim vendorID As Integer  
  
    Dim vendorCmd As SqlCommand  
    Dim productCmd As SqlCommand  
    Dim productReader As SqlDataReader  
  
    Dim vendorSQL As String = & _
      "SELECT VendorId, Name FROM Purchasing.Vendor"  
    Dim productSQL As String = _  
        "SELECT Production.Product.Name FROM Production.Product " & _  
        "INNER JOIN Purchasing.ProductVendor " & _  
        "ON Production.Product.ProductID = " & _  
        "Purchasing.ProductVendor.ProductID " & _  
        "WHERE Purchasing.ProductVendor.VendorID = @VendorId"  
  
    Using awConnection As New SqlConnection(connectionString)  
      vendorCmd = New SqlCommand(vendorSQL, awConnection)  
      productCmd = New SqlCommand(productSQL, awConnection)  
      productCmd.Parameters.Add("@VendorId", SqlDbType.Int)  
  
      awConnection.Open()  
      Using vendorReader As SqlDataReader = vendorCmd.ExecuteReader()  
        While vendorReader.Read()  
          Console.WriteLine(vendorReader("Name"))  
  
          vendorID = CInt(vendorReader("VendorId"))  
  
          productCmd.Parameters("@VendorId").Value = vendorID  
  
          ' The following line of code requires  
          ' a MARS-enabled connection.  
          productReader = productCmd.ExecuteReader()  
          Using productReader  
            While productReader.Read()  
              Console.WriteLine("  " & CStr(productReader("Name")))  
            End While  
          End Using  
        End While  
      End Using  
    End Using  
  
    Console.WriteLine("Press any key to continue")  
    Console.ReadLine()  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=(local);Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks; MultipleActiveResultSets=True"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  // By default, MARS is disabled when connecting  
  // to a MARS-enabled host.  
  // It must be enabled in the connection string.  
  string connectionString = GetConnectionString();  
  
  int vendorID;  
  SqlDataReader productReader = null;  
  string vendorSQL =
    "SELECT VendorId, Name FROM Purchasing.Vendor";  
  string productSQL =
    "SELECT Production.Product.Name FROM Production.Product " +  
    "INNER JOIN Purchasing.ProductVendor " +  
    "ON Production.Product.ProductID = " +
    "Purchasing.ProductVendor.ProductID " +  
    "WHERE Purchasing.ProductVendor.VendorID = @VendorId";  
  
  using (SqlConnection awConnection =
    new SqlConnection(connectionString))  
  {  
    SqlCommand vendorCmd = new SqlCommand(vendorSQL, awConnection);  
    SqlCommand productCmd =
      new SqlCommand(productSQL, awConnection);  
  
    productCmd.Parameters.Add("@VendorId", SqlDbType.Int);  
  
    awConnection.Open();  
    using (SqlDataReader vendorReader = vendorCmd.ExecuteReader())  
    {  
      while (vendorReader.Read())  
      {  
        Console.WriteLine(vendorReader["Name"]);  
  
        vendorID = (int)vendorReader["VendorId"];  
  
        productCmd.Parameters["@VendorId"].Value = vendorID;  
        // The following line of code requires  
        // a MARS-enabled connection.  
        productReader = productCmd.ExecuteReader();  
        using (productReader)  
        {  
          while (productReader.Read())  
          {  
            Console.WriteLine("  " +  
              productReader["Name"].ToString());  
          }  
        }  
      }  
  }  
      Console.WriteLine("Press any key to continue");  
      Console.ReadLine();  
    }  
  }  
  private static string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,  
    // you can retrieve it from a configuration file.  
    return "Data Source=(local);Integrated Security=SSPI;" +
      "Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";  
  }  
}  
```  
  
## <a name="reading-and-updating-data-with-mars"></a><span data-ttu-id="90569-116">Lectura y actualización de datos con MARS</span><span class="sxs-lookup"><span data-stu-id="90569-116">Reading and Updating Data with MARS</span></span>  

 <span data-ttu-id="90569-117">MARS permite usar una conexión para operaciones de lectura y de lenguaje de manipulación de datos (DML) con más de una operación pendiente.</span><span class="sxs-lookup"><span data-stu-id="90569-117">MARS allows a connection to be used for both read operations and data manipulation language (DML) operations with more than one pending operation.</span></span> <span data-ttu-id="90569-118">Esta característica elimina la necesidad de que una aplicación se ocupe de los errores de conexión ocupada.</span><span class="sxs-lookup"><span data-stu-id="90569-118">This feature eliminates the need for an application to deal with connection-busy errors.</span></span> <span data-ttu-id="90569-119">Además, MARS puede reemplazar el uso de los cursores del lado servidor, que suelen consumir más recursos.</span><span class="sxs-lookup"><span data-stu-id="90569-119">In addition, MARS can replace the use of server-side cursors, which generally consume more resources.</span></span> <span data-ttu-id="90569-120">Finalmente, dado que es posible realizar varias operaciones con una sola conexión, pueden compartir el mismo contexto de transacción, lo que elimina la necesidad de usar los procedimientos almacenados del sistema **sp_getbindtoken** y **sp_bindsession**.</span><span class="sxs-lookup"><span data-stu-id="90569-120">Finally, because multiple operations can operate on a single connection, they can share the same transaction context, eliminating the need to use **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span>  
  
### <a name="example"></a><span data-ttu-id="90569-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90569-121">Example</span></span>  

 <span data-ttu-id="90569-122">La siguiente aplicación de consola muestra cómo usar dos objetos <xref:System.Data.SqlClient.SqlDataReader> con tres objetos <xref:System.Data.SqlClient.SqlCommand> y un único objeto <xref:System.Data.SqlClient.SqlConnection> con MARS habilitado.</span><span class="sxs-lookup"><span data-stu-id="90569-122">The following Console application demonstrates how to use two <xref:System.Data.SqlClient.SqlDataReader> objects with three <xref:System.Data.SqlClient.SqlCommand> objects and a single <xref:System.Data.SqlClient.SqlConnection> object with MARS enabled.</span></span> <span data-ttu-id="90569-123">El primer objeto de comando recupera una lista de proveedores cuya clasificación crediticia es 5.</span><span class="sxs-lookup"><span data-stu-id="90569-123">The first command object retrieves a list of vendors whose credit rating is 5.</span></span> <span data-ttu-id="90569-124">El segundo objeto de comando utiliza el identificador de proveedor proporcionado a partir de <xref:System.Data.SqlClient.SqlDataReader> para cargar el segundo <xref:System.Data.SqlClient.SqlDataReader> con todos los productos de ese proveedor en particular.</span><span class="sxs-lookup"><span data-stu-id="90569-124">The second command object uses the vendor ID provided from a <xref:System.Data.SqlClient.SqlDataReader> to load the second <xref:System.Data.SqlClient.SqlDataReader> with all of the products for the particular vendor.</span></span> <span data-ttu-id="90569-125">El segundo <xref:System.Data.SqlClient.SqlDataReader> visita cada registro del producto.</span><span class="sxs-lookup"><span data-stu-id="90569-125">Each product record is visited by the second <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="90569-126">Para determinar cuál debe ser la nueva **OnOrderQty**, se realiza un cálculo.</span><span class="sxs-lookup"><span data-stu-id="90569-126">A calculation is performed to determine what the new **OnOrderQty** should be.</span></span> <span data-ttu-id="90569-127">Luego, se usa el tercer objeto de comando para actualizar la tabla **ProductVendor** con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="90569-127">The third command object is then used to update the **ProductVendor** table with the new value.</span></span> <span data-ttu-id="90569-128">Este proceso completo tiene lugar dentro de una única transacción, que se revierte al final.</span><span class="sxs-lookup"><span data-stu-id="90569-128">This entire process takes place within a single transaction, which is rolled back at the end.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90569-129">En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="90569-129">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="90569-130">La cadena de conexión proporcionada en el código de ejemplo da por sentado que la base de datos está instalada y disponible en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="90569-130">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="90569-131">Modifique la cadena de conexión según sea necesario para el entorno.</span><span class="sxs-lookup"><span data-stu-id="90569-131">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
Option Explicit On  
  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    ' By default, MARS is disabled when connecting  
    ' to a MARS-enabled host.  
    ' It must be enabled in the connection string.  
    Dim connectionString As String = GetConnectionString()  
  
    Dim updateTx As SqlTransaction  
    Dim vendorCmd As SqlCommand  
    Dim prodVendCmd As SqlCommand  
    Dim updateCmd As SqlCommand  
  
    Dim prodVendReader As SqlDataReader  
  
    Dim vendorID As Integer  
    Dim productID As Integer  
    Dim minOrderQty As Integer  
    Dim maxOrderQty As Integer  
    Dim onOrderQty As Integer  
    Dim recordsUpdated As Integer  
    Dim totalRecordsUpdated As Integer  
  
    Dim vendorSQL As String = _  
        "SELECT VendorID, Name FROM Purchasing.Vendor " & _  
        "WHERE CreditRating = 5"  
    Dim prodVendSQL As String = _  
        "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " & _  
        "FROM Purchasing.ProductVendor " & _  
        "WHERE VendorID = @VendorID"  
    Dim updateSQL As String = _  
        "UPDATE Purchasing.ProductVendor " & _
        "SET OnOrderQty = @OrderQty " & _  
        "WHERE ProductID = @ProductID AND VendorID = @VendorID"  
  
    Using awConnection As New SqlConnection(connectionString)  
      awConnection.Open()  
      updateTx = awConnection.BeginTransaction()  
  
      vendorCmd = New SqlCommand(vendorSQL, awConnection)  
      vendorCmd.Transaction = updateTx  
  
      prodVendCmd = New SqlCommand(prodVendSQL, awConnection)  
      prodVendCmd.Transaction = updateTx  
      prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int)  
  
      updateCmd = New SqlCommand(updateSQL, awConnection)  
      updateCmd.Transaction = updateTx  
      updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int)  
      updateCmd.Parameters.Add("@ProductID", SqlDbType.Int)  
      updateCmd.Parameters.Add("@VendorID", SqlDbType.Int)  
  
      Using vendorReader As SqlDataReader = vendorCmd.ExecuteReader()  
        While vendorReader.Read()  
          Console.WriteLine(vendorReader("Name"))  
  
          vendorID = CInt(vendorReader("VendorID"))  
          prodVendCmd.Parameters("@VendorID").Value = vendorID  
          prodVendReader = prodVendCmd.ExecuteReader()  
  
          Using prodVendReader  
            While (prodVendReader.Read)  
              productID = CInt(prodVendReader("ProductID"))  
  
              If IsDBNull(prodVendReader("OnOrderQty")) Then  
                minOrderQty = CInt(prodVendReader("MinOrderQty"))  
                onOrderQty = minOrderQty  
              Else  
                maxOrderQty = CInt(prodVendReader("MaxOrderQty"))  
                onOrderQty = CInt(maxOrderQty / 2)  
              End If  
  
              updateCmd.Parameters("@OrderQty").Value = onOrderQty  
              updateCmd.Parameters("@ProductID").Value = productID  
              updateCmd.Parameters("@VendorID").Value = vendorID  
  
              recordsUpdated = updateCmd.ExecuteNonQuery()  
              totalRecordsUpdated += recordsUpdated  
            End While  
          End Using  
        End While  
      End Using  
  
      Console.WriteLine("Total Records Updated: " & _
        CStr(totalRecordsUpdated))  
      updateTx.Rollback()  
      Console.WriteLine("Transaction Rolled Back")  
    End Using  
  
    Console.WriteLine("Press any key to continue")  
    Console.ReadLine()  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=(local);Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks;MultipleActiveResultSets=True"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
static void Main()  
{  
  // By default, MARS is disabled when connecting  
  // to a MARS-enabled host.  
  // It must be enabled in the connection string.  
  string connectionString = GetConnectionString();  
  
  SqlTransaction updateTx = null;  
  SqlCommand vendorCmd = null;  
  SqlCommand prodVendCmd = null;  
  SqlCommand updateCmd = null;  
  
  SqlDataReader prodVendReader = null;  
  
  int vendorID = 0;  
  int productID = 0;  
  int minOrderQty = 0;  
  int maxOrderQty = 0;  
  int onOrderQty = 0;  
  int recordsUpdated = 0;  
  int totalRecordsUpdated = 0;  
  
  string vendorSQL =  
      "SELECT VendorID, Name FROM Purchasing.Vendor " +
      "WHERE CreditRating = 5";  
  string prodVendSQL =  
      "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " +  
      "FROM Purchasing.ProductVendor " +
      "WHERE VendorID = @VendorID";  
  string updateSQL =  
      "UPDATE Purchasing.ProductVendor " +
      "SET OnOrderQty = @OrderQty " +  
      "WHERE ProductID = @ProductID AND VendorID = @VendorID";  
  
  using (SqlConnection awConnection =
    new SqlConnection(connectionString))  
  {  
    awConnection.Open();  
    updateTx = awConnection.BeginTransaction();  
  
    vendorCmd = new SqlCommand(vendorSQL, awConnection);  
    vendorCmd.Transaction = updateTx;  
  
    prodVendCmd = new SqlCommand(prodVendSQL, awConnection);  
    prodVendCmd.Transaction = updateTx;  
    prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int);  
  
    updateCmd = new SqlCommand(updateSQL, awConnection);  
    updateCmd.Transaction = updateTx;  
    updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int);  
    updateCmd.Parameters.Add("@ProductID", SqlDbType.Int);  
    updateCmd.Parameters.Add("@VendorID", SqlDbType.Int);  
  
    using (SqlDataReader vendorReader = vendorCmd.ExecuteReader())  
    {  
      while (vendorReader.Read())  
      {  
        Console.WriteLine(vendorReader["Name"]);  
  
        vendorID = (int) vendorReader["VendorID"];  
        prodVendCmd.Parameters["@VendorID"].Value = vendorID;  
        prodVendReader = prodVendCmd.ExecuteReader();  
  
        using (prodVendReader)  
        {  
          while (prodVendReader.Read())  
          {  
            productID = (int) prodVendReader["ProductID"];  
  
            if (prodVendReader["OnOrderQty"] == DBNull.Value)  
            {  
              minOrderQty = (int) prodVendReader["MinOrderQty"];  
              onOrderQty = minOrderQty;  
            }  
            else  
            {  
              maxOrderQty = (int) prodVendReader["MaxOrderQty"];  
              onOrderQty = (int)(maxOrderQty / 2);  
            }  
  
            updateCmd.Parameters["@OrderQty"].Value = onOrderQty;  
            updateCmd.Parameters["@ProductID"].Value = productID;  
            updateCmd.Parameters["@VendorID"].Value = vendorID;  
  
            recordsUpdated = updateCmd.ExecuteNonQuery();  
            totalRecordsUpdated += recordsUpdated;  
          }  
        }  
      }  
    }  
    Console.WriteLine("Total Records Updated: " +
      totalRecordsUpdated.ToString());  
    updateTx.Rollback();  
    Console.WriteLine("Transaction Rolled Back");  
  }  
  
  Console.WriteLine("Press any key to continue");  
  Console.ReadLine();  
}  
private static string GetConnectionString()  
{  
  // To avoid storing the connection string in your code,  
  // you can retrieve it from a configuration file.  
  return "Data Source=(local);Integrated Security=SSPI;" +
    "Initial Catalog=AdventureWorks;" +
    "MultipleActiveResultSets=True";  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="90569-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="90569-132">See also</span></span>

- [<span data-ttu-id="90569-133">Conjuntos de resultados activos múltiples (MARS)</span><span class="sxs-lookup"><span data-stu-id="90569-133">Multiple Active Result Sets (MARS)</span></span>](multiple-active-result-sets-mars.md)
- [<span data-ttu-id="90569-134">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="90569-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
