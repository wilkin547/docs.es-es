---
title: Especificar valores XML como parámetros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2c4d08b8-fc29-4614-97fa-29c8ff7ca5b3
ms.openlocfilehash: 8e57bfe23a80bf3913cd7fb8b96527870259e77a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780876"
---
# <a name="specifying-xml-values-as-parameters"></a><span data-ttu-id="31a2f-102">Especificar valores XML como parámetros</span><span class="sxs-lookup"><span data-stu-id="31a2f-102">Specifying XML Values as Parameters</span></span>
<span data-ttu-id="31a2f-103">Si una consulta requiere un parámetro cuyo valor es una cadena XML, los desarrolladores pueden proporcionar ese valor mediante una instancia del tipo de datos **SQLXML** .</span><span class="sxs-lookup"><span data-stu-id="31a2f-103">If a query requires a parameter whose value is an XML string, developers can supply that value using an instance of the **SqlXml** data type.</span></span> <span data-ttu-id="31a2f-104">En realidad, no hay trucos; Las columnas XML de SQL Server aceptan valores de parámetro exactamente del mismo modo que otros tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="31a2f-104">There really are no tricks; XML columns in SQL Server accept parameter values in exactly the same way as other data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31a2f-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31a2f-105">Example</span></span>  
 <span data-ttu-id="31a2f-106">La siguiente aplicación de consola crea una nueva tabla en la base de datos **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="31a2f-106">The following console application creates a new table in the **AdventureWorks** database.</span></span> <span data-ttu-id="31a2f-107">La nueva tabla incluye una columna denominada **SalesID** y una columna XML denominada **SalesInfo**.</span><span class="sxs-lookup"><span data-stu-id="31a2f-107">The new table includes a column named **SalesID** and an XML column named **SalesInfo**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31a2f-108">La base de datos de ejemplo **AdventureWorks** no se instala de forma predeterminada al instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31a2f-108">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="31a2f-109">Para instalarla, ejecute el programa de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="31a2f-109">You can install it by running SQL Server Setup.</span></span>  
  
 <span data-ttu-id="31a2f-110">En el ejemplo se prepara un objeto <xref:System.Data.SqlClient.SqlCommand> para insertar una fila en la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="31a2f-110">The example prepares a <xref:System.Data.SqlClient.SqlCommand> object to insert a row in the new table.</span></span> <span data-ttu-id="31a2f-111">Un archivo guardado proporciona los datos XML necesarios para la columna **SalesInfo** .</span><span class="sxs-lookup"><span data-stu-id="31a2f-111">A saved file provides the XML data needed for the **SalesInfo** column.</span></span>  
  
 <span data-ttu-id="31a2f-112">Para crear el archivo necesario para el ejemplo que se va a ejecutar, cree un nuevo archivo de texto en la misma carpeta que el proyecto.</span><span class="sxs-lookup"><span data-stu-id="31a2f-112">To create the file needed for the example to run, create a new text file in the same folder as your project.</span></span> <span data-ttu-id="31a2f-113">Asigne al archivo el nombre MyTestStoreData.xml.</span><span class="sxs-lookup"><span data-stu-id="31a2f-113">Name the file MyTestStoreData.xml.</span></span> <span data-ttu-id="31a2f-114">Abra el archivo en el Bloc de notas y copie y pegue el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="31a2f-114">Open the file in Notepad and copy and paste the following text:</span></span>  
  
```xml  
<StoreSurvey xmlns="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>International Bank</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1970</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>7000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>T1</Internet>  
  <NumberEmployees>2</NumberEmployees>  
</StoreSurvey>  
```  
  
```vb  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Xml  
  
Module Module1  
    Sub Main()  
  
        Using connection As SqlConnection = New SqlConnection(GetConnectionString())  
        connection.Open()  
  
        ' Create a sample table (dropping first if it already  
        ' exists.)  
        Dim commandNewTable As String = _  
         "IF EXISTS (SELECT * FROM dbo.sysobjects " & _  
         "WHERE id = object_id(N'[dbo].[XmlDataTypeSample]') " & _  
         "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " & _  
         "DROP TABLE [dbo].[XmlDataTypeSample];" & _  
         "CREATE TABLE [dbo].[XmlDataTypeSample](" & _  
         "[SalesID] [int] IDENTITY(1,1) NOT NULL, " & _  
         "[SalesInfo] [xml])"  
  
        Dim commandAdd As New _  
         SqlCommand(commandNewTable, connection)  
        commandAdd.ExecuteNonQuery()  
  
        Dim commandText As String = _  
         "INSERT INTO [dbo].[XmlDataTypeSample] " & _  
           "([SalesInfo] ) " & _  
           "VALUES(@xmlParameter )"  
  
        Dim command As New SqlCommand(commandText, connection)  
  
        ' Read the saved XML document as a   
        ' SqlXml-data typed variable.  
        Dim newXml As SqlXml = _  
         New SqlXml(New XmlTextReader("MyTestStoreData.xml"))  
  
        ' Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml)  
  
        Dim result As Integer = command.ExecuteNonQuery()  
        Console.WriteLine(result & " row was added.")  
        Console.WriteLine("Press Enter to continue.")  
        Console.ReadLine()  
    End Using  
End Sub  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,              
        ' you can retrieve it from a configuration file.   
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Xml;  
using System.Data.SqlTypes;  
  
class Class1  
{  
    static void Main()  
    {  
        using (SqlConnection connection = new SqlConnection(GetConnectionString()))  
       {  
        connection.Open();  
        //  Create a sample table (dropping first if it already  
        //  exists.)  
  
        string commandNewTable =   
            "IF EXISTS (SELECT * FROM dbo.sysobjects " +   
            "WHERE id = " +  
                  "object_id(N'[dbo].[XmlDataTypeSample]') " +   
            "AND OBJECTPROPERTY(id, N'IsUserTable') = 1) " +   
            "DROP TABLE [dbo].[XmlDataTypeSample];" +   
            "CREATE TABLE [dbo].[XmlDataTypeSample](" +   
            "[SalesID] [int] IDENTITY(1,1) NOT NULL, " +   
            "[SalesInfo] [xml])";  
        SqlCommand commandAdd =   
                   new SqlCommand(commandNewTable, connection);  
        commandAdd.ExecuteNonQuery();  
        string commandText =   
            "INSERT INTO [dbo].[XmlDataTypeSample] " +   
            "([SalesInfo] ) " +   
            "VALUES(@xmlParameter )";  
        SqlCommand command =   
                  new SqlCommand(commandText, connection);  
  
        //  Read the saved XML document as a   
        //  SqlXml-data typed variable.  
        SqlXml newXml =   
            new SqlXml(new XmlTextReader("MyTestStoreData.xml"));  
  
        //  Supply the SqlXml value for the value of the parameter.  
        command.Parameters.AddWithValue("@xmlParameter", newXml);  
  
        int result = command.ExecuteNonQuery();  
        Console.WriteLine(result + " row was added.");  
        Console.WriteLine("Press Enter to continue.");  
        Console.ReadLine();  
    }  
  }  
  
    private static string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,              
        // you can retrieve it from a configuration file.   
        return "Data Source=(local);Integrated Security=true;" +  
        "Initial Catalog=AdventureWorks; ";  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="31a2f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="31a2f-115">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="31a2f-116">Datos XML en SQL Server</span><span class="sxs-lookup"><span data-stu-id="31a2f-116">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="31a2f-117">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="31a2f-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
