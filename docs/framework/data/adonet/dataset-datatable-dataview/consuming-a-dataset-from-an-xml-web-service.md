---
title: Consumir un conjunto de información desde un servicio Web XML
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: e6dc32274cc3b0d7ec9d66a837a422c87fb2468b
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416214"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a>Consumir un conjunto de información desde un servicio Web XML

La arquitectura del <xref:System.Data.DataSet> tiene un diseño desconectado, en parte para facilitar el transporte de datos a través de Internet. El **conjunto** de datos es "serializable", ya que se puede especificar como entrada o salida de los servicios Web XML sin necesidad de codificación adicional necesaria para transmitir por secuencias el contenido del **conjunto** de datos desde un servicio Web XML a un cliente y viceversa. El **DataSet** se convierte implícitamente en una secuencia XML mediante el formato DiffGram, se envía a través de la red y, a continuación, se reconstruye a partir de la secuencia XML como un conjunto de un **conjunto** de información en el extremo receptor. Esto ofrece un método sencillo y flexible para transmitir y devolver datos relacionales mediante servicios Web XML. Para obtener más información sobre el formato DiffGram, vea [DiffGrams](diffgrams.md).  
  
 En el ejemplo siguiente se muestra cómo crear un servicio Web XML y un cliente que utiliza el **conjunto** de datos para transportar datos relacionales (incluidos los datos modificados) y resolver de nuevo las actualizaciones en el origen de datos original.  
  
> [!NOTE]
> La transmisión `DataSet` `DataTable` de instancias o como parte de llamadas a servicios Web XML no es segura si la entrada no es de confianza. Para obtener más información, consulte la [Guía de seguridad DataSet y DataTable](security-guidance.md).
> También se recomienda tener en cuenta las implicaciones de seguridad al crear un servicio Web XML. Para obtener información sobre cómo proteger un servicio Web XML, vea [proteger los servicios Web XML creados con ASP.net](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).  
  
## <a name="create-an-xml-web-service"></a>Crear un servicio Web XML
  
1. Cree el servicio Web XML.  
  
     En el ejemplo, se crea un servicio Web XML que devuelve datos, en este caso una lista de clientes de la base de datos **Northwind** , y recibe un **conjunto** de datos con actualizaciones de los datos, que el servicio Web XML resuelve de nuevo en el origen de datos original.  
  
     El servicio Web XML expone dos métodos: **GetCustomers**, para devolver la lista de clientes, y **UpdateCustomers**, para resolver las actualizaciones de nuevo en el origen de datos. El servicio Web XML se almacena en un archivo del servidor web denominado DataSetSample.asmx. En el siguiente código se describe el contenido de DataSetSample.asmx.  
  
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
  
     En un escenario típico, el método **UpdateCustomers** se escribiría para detectar infracciones de simultaneidad optimista. Para simplificar, el ejemplo no lo incluye. Para obtener más información sobre la simultaneidad optimista, consulte [simultaneidad optimista](../optimistic-concurrency.md).  
  
2. Cree un proxy de servicio Web XML.  
  
     Los clientes del servicio Web XML necesitan un proxy SOAP para utilizar los métodos expuestos. Visual Studio puede generar el proxy. Al establecer una referencia Web a un servicio Web existente desde Visual Studio, el comportamiento descrito en este paso se produce de forma transparente. Si desea crear la clase de proxy personalmente, continúe con la explicación. Sin embargo, el uso de Visual Studio para crear la clase de proxy para la aplicación cliente es suficiente en la mayoría de los casos.  
  
     Es posible crear un proxy con la herramienta Lenguaje de descripción de servicios Web. Por ejemplo, si el servicio Web XML se expone en la dirección URL `http://myserver/data/DataSetSample.asmx` , emita un comando como el siguiente para crear un Visual Basic proxy .net con un espacio de nombres de **webdata. DSSample** y almacenarlo en el archivo Sample. VB.  
  
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
  
3. Cree un cliente de servicio Web XML.  
  
     Si desea que Visual Studio genere la clase de proxy de servicio Web automáticamente, simplemente cree el proyecto de cliente y, en la ventana de explorador de soluciones, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar**  >  **referencia de servicio**. En el cuadro de diálogo **Agregar referencia de servicio** , seleccione **avanzadas**y, a continuación, seleccione **Agregar referencia Web**. Seleccione el servicio Web en la lista de servicios web disponibles (esto puede requerir que se proporcione la dirección del extremo de servicio Web si el servicio Web no está disponible en la solución actual o en el equipo actual). Si crea el proxy del servicio Web XML personalmente, tal y como se describe en el paso anterior, puede importarlo en el código de cliente y utilizar los métodos de servicio Web XML.

     En el código de ejemplo siguiente se importa la biblioteca de proxy, se llama a **GetCustomers** para obtener una lista de clientes, se agrega un nuevo cliente y, a continuación, se devuelve un **conjunto** de elementos con las actualizaciones a **UpdateCustomers**.  
  
     En el ejemplo se pasa el **conjunto** de resultados devuelto por **DataSet. GetChanges** a **UpdateCustomers** porque solo es necesario pasar las filas modificadas a **UpdateCustomers**. **UpdateCustomers** devuelve el **conjunto**de datos resuelto, que se puede **combinar** en el **conjunto** de datos existente para incorporar los cambios resueltos y cualquier información de error de fila de la actualización. En el código siguiente se supone que ha utilizado Visual Studio para crear la referencia Web y que ha cambiado el nombre de la referencia Web a DsSample en el cuadro de diálogo **Agregar referencia Web** .  
  
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
  
## <a name="see-also"></a>Consulte también

- [ADO.NET](../index.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Objetos DataTable](datatables.md)
- [Rellenar un conjunto de datos desde un objeto DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Actualizar orígenes de datos con objetos DataAdapter](../updating-data-sources-with-dataadapters.md)
- [Parámetros de DataAdapter](../dataadapter-parameters.md)
- [Herramienta lenguaje de descripción de servicios web (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))
- [Información general de ADO.NET](../ado-net-overview.md)
