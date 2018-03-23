---
title: Utilizar un conjunto de datos desde un servicio Web XML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 9bfcd4d8dca38c9438c072c143cf7ba0eafd6ecf
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a>Utilizar un conjunto de datos desde un servicio Web XML
La arquitectura del <xref:System.Data.DataSet> tiene un diseño desconectado, en parte para facilitar el transporte de datos a través de Internet. El **conjunto de datos** es "serializable" en que puede especificarse como entrada o salida de los servicios Web XML sin ninguna codificación adicional necesario para transmitir el contenido de la **conjunto de datos** desde un servicio Web XML para un cliente y viceversa. El **conjunto de datos** se convierte implícitamente en una secuencia XML mediante el formato DiffGram, enviados a través de la red y se reconstruye a partir de la secuencia XML como un **conjunto de datos** en el extremo receptor. Esto proporciona un método muy sencillo y flexible para transmitir y devolver datos relacionales mediante servicios Web XML. Para obtener más información acerca del formato DiffGram, vea [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).  
  
 En el ejemplo siguiente se muestra cómo crear un servicio Web XML y los clientes que usan el **conjunto de datos** para transportar datos relacionales (incluyendo datos modificados) y resolver cualquier actualización en el origen de datos.  
  
> [!NOTE]
>  Al crear un servicio Web XML, es recomendable tener siempre en cuenta las implicaciones de seguridad. Para obtener información sobre cómo proteger un servicio Web XML, vea [proteger servicios Web XML creados con ASP.NET](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c).  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a>Para crear un servicio Web XML que devuelve y consume un DataSet  
  
1.  Cree el servicio Web XML.  
  
     En el ejemplo, se crea un servicio Web XML que devuelve datos, en este caso una lista de clientes de la **Northwind** la base de datos y recibe un **conjunto de datos** con las actualizaciones a los datos, que el servicio Web XML resuelve y devuelve al origen de datos original.  
  
     El servicio Web XML expone dos métodos: **GetCustomers**para devolver la lista de clientes, y **UpdateCustomers**, para resolver las actualizaciones en el origen de datos. El servicio Web XML se almacena en un archivo del servidor web denominado DataSetSample.asmx. En el siguiente código se describe el contenido de DataSetSample.asmx.  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     En un escenario típico, el **UpdateCustomers** se escribiría el método para detectar las infracciones de simultaneidad optimista. Para simplificar, el ejemplo no lo incluye. Para obtener más información acerca de la simultaneidad optimista, vea [simultaneidad optimista](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).  
  
2.  Cree un proxy de servicio Web XML.  
  
     Los clientes del servicio Web XML necesitan un proxy SOAP para utilizar los métodos expuestos. Visual Studio puede generar el proxy. Al establecer una referencia Web a un servicio Web existente desde Visual Studio, el comportamiento descrito en este paso se produce de forma transparente. Si desea crear la clase de proxy personalmente, continúe con la explicación. Sin embargo, el uso de Visual Studio para crear la clase de proxy para la aplicación cliente es suficiente en la mayoría de los casos.  
  
     Es posible crear un proxy con la herramienta Lenguaje de descripción de servicios Web. Por ejemplo, si el servicio Web XML se expone en la dirección URL http://myserver/data/DataSetSample.asmx, emitir un comando como el siguiente para crear un proxy de Visual Basic .NET con un espacio de nombres de **WebData.DSSample** y almacenarlo en el archivo Sample.vb.  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Para crear un proxy de C# en el archivo sample.cs, hay que utilizar el comando siguiente.  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     El proxy puede compilarse como una biblioteca e importarse en el cliente del servicio Web XML. Para compilar el código de proxy de Visual Basic .NET almacenado en sample.vb como sample.dll, hay que utilizar el siguiente comando.  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     Para compilar el código de proxy de C# almacenado en sample.cs como sample.dll, hay que utilizar el siguiente comando.  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3.  Cree un cliente de servicio Web XML.  
  
     Si desea que Visual Studio genere la clase de proxy de servicio Web para usted, simplemente cree el proyecto de cliente y, en la ventana Explorador de soluciones, haga clic en el proyecto, haga clic en **Agregar referencia Web**y seleccione el servicio Web de la lista de servicios Web disponibles (Esto puede requerir proporcionando la dirección del extremo del servicio Web, si el servicio Web no está disponible dentro de la solución actual o en el equipo actual.) Si crea el proxy del servicio Web XML personalmente, tal y como se describe en el paso anterior, puede importarlo en el código de cliente y utilizar los métodos de servicio Web XML. El código de ejemplo siguiente importa la biblioteca de proxy, llamadas **GetCustomers** obtener una lista de clientes, agrega un nuevo cliente y, a continuación, devuelve un **conjunto de datos** con las actualizaciones a **UpdateCustomers** .  
  
     Tenga en cuenta que el ejemplo pasa el **conjunto de datos** devuelto por **DataSet.GetChanges** a **UpdateCustomers** porque solo las filas modificadas deben pasarse a  **UpdateCustomers**. **UpdateCustomers** devuelve el resuelto **conjunto de datos**, que puede, a continuación, **mezcla** existentes **conjunto de datos** para incorporar los cambios resueltos y cualquier información de error de fila de la actualización. El código siguiente se da por supuesto que ha utilizado Visual Studio para crear la referencia Web y que ha cambiado el nombre de la referencia Web a DsSample en el **Agregar referencia Web** cuadro de diálogo.  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =   
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     Si decide crear la clase de proxy personalmente, debe seguir los pasos adicionales que se describen a continuación. Para compilar el ejemplo, indique la biblioteca de proxy creada (sample.dll) y las bibliotecas de .NET relacionadas. Para compilar la versión de Visual Basic .NET del ejemplo, almacenada en el archivo client.vb, hay que utilizar el comando siguiente.  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     Para compilar la versión de C# del ejemplo, almacenada en el archivo client.cs, hay que utilizar el comando siguiente.  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a>Vea también  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [Actualizar orígenes de datos con objetos DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [Parámetros de DataAdapter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [Web Services Description Language Tool (Wsdl.exe)](https://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
