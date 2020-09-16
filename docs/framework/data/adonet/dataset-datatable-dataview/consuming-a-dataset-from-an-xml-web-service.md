---
title: Consumir un conjunto de información desde un servicio Web XML
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: d4f4d5d34698fbb9a7986f4628b282d4425da3f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554702"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="5fc41-102">Consumir un conjunto de información desde un servicio Web XML</span><span class="sxs-lookup"><span data-stu-id="5fc41-102">Consume a DataSet from an XML web service</span></span>

<span data-ttu-id="5fc41-103">La arquitectura del <xref:System.Data.DataSet> tiene un diseño desconectado, en parte para facilitar el transporte de datos a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="5fc41-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="5fc41-104">El **conjunto** de datos es "serializable", ya que se puede especificar como entrada o salida de los servicios Web XML sin necesidad de codificación adicional necesaria para transmitir por secuencias el contenido del **conjunto** de datos desde un servicio Web XML a un cliente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="5fc41-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="5fc41-105">El **DataSet** se convierte implícitamente en una secuencia XML mediante el formato DiffGram, se envía a través de la red y, a continuación, se reconstruye a partir de la secuencia XML como un conjunto de un **conjunto** de información en el extremo receptor.</span><span class="sxs-lookup"><span data-stu-id="5fc41-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="5fc41-106">Esto ofrece un método sencillo y flexible para transmitir y devolver datos relacionales mediante servicios Web XML.</span><span class="sxs-lookup"><span data-stu-id="5fc41-106">This gives you a simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="5fc41-107">Para obtener más información sobre el formato DiffGram, vea [DiffGrams](diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="5fc41-107">For more information about the DiffGram format, see [DiffGrams](diffgrams.md).</span></span>  
  
 <span data-ttu-id="5fc41-108">En el ejemplo siguiente se muestra cómo crear un servicio Web XML y un cliente que utiliza el **conjunto** de datos para transportar datos relacionales (incluidos los datos modificados) y resolver de nuevo las actualizaciones en el origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="5fc41-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fc41-109">La transmisión `DataSet` `DataTable` de instancias o como parte de llamadas a servicios Web XML no es segura si la entrada no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="5fc41-109">Transmitting `DataSet` or `DataTable` instances as part of XML Web service calls is not safe if the input is not trusted.</span></span> <span data-ttu-id="5fc41-110">Para obtener más información, consulte la [Guía de seguridad DataSet y DataTable](security-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="5fc41-110">For more information, see [DataSet and DataTable security guidance](security-guidance.md).</span></span>
> <span data-ttu-id="5fc41-111">También se recomienda tener en cuenta las implicaciones de seguridad al crear un servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="5fc41-111">We also recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="5fc41-112">Para obtener información sobre cómo proteger un servicio Web XML, vea [proteger los servicios Web XML creados con ASP.net](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5fc41-112">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
## <a name="create-an-xml-web-service"></a><span data-ttu-id="5fc41-113">Crear un servicio Web XML</span><span class="sxs-lookup"><span data-stu-id="5fc41-113">Create an XML web service</span></span>
  
1. <span data-ttu-id="5fc41-114">Cree el servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="5fc41-114">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="5fc41-115">En el ejemplo, se crea un servicio Web XML que devuelve datos, en este caso una lista de clientes de la base de datos **Northwind** , y recibe un **conjunto** de datos con actualizaciones de los datos, que el servicio Web XML resuelve de nuevo en el origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="5fc41-115">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="5fc41-116">El servicio Web XML expone dos métodos: **GetCustomers**, para devolver la lista de clientes, y **UpdateCustomers**, para resolver las actualizaciones de nuevo en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fc41-116">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="5fc41-117">El servicio Web XML se almacena en un archivo del servidor web denominado DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="5fc41-117">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="5fc41-118">En el siguiente código se describe el contenido de DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="5fc41-118">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
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
  
     <span data-ttu-id="5fc41-119">En un escenario típico, el método **UpdateCustomers** se escribiría para detectar infracciones de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="5fc41-119">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="5fc41-120">Para simplificar, el ejemplo no lo incluye.</span><span class="sxs-lookup"><span data-stu-id="5fc41-120">For simplicity, the example does not include this.</span></span> <span data-ttu-id="5fc41-121">Para obtener más información sobre la simultaneidad optimista, consulte [simultaneidad optimista](../optimistic-concurrency.md).</span><span class="sxs-lookup"><span data-stu-id="5fc41-121">For more information about optimistic concurrency, see [Optimistic Concurrency](../optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="5fc41-122">Cree un proxy de servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="5fc41-122">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="5fc41-123">Los clientes del servicio Web XML necesitan un proxy SOAP para utilizar los métodos expuestos.</span><span class="sxs-lookup"><span data-stu-id="5fc41-123">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="5fc41-124">Visual Studio puede generar el proxy.</span><span class="sxs-lookup"><span data-stu-id="5fc41-124">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="5fc41-125">Al establecer una referencia Web a un servicio Web existente desde Visual Studio, el comportamiento descrito en este paso se produce de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="5fc41-125">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="5fc41-126">Si desea crear la clase de proxy personalmente, continúe con la explicación.</span><span class="sxs-lookup"><span data-stu-id="5fc41-126">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="5fc41-127">Sin embargo, el uso de Visual Studio para crear la clase de proxy para la aplicación cliente es suficiente en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="5fc41-127">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="5fc41-128">Es posible crear un proxy con la herramienta Lenguaje de descripción de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="5fc41-128">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="5fc41-129">Por ejemplo, si el servicio Web XML se expone en la dirección URL `http://myserver/data/DataSetSample.asmx` , emita un comando como el siguiente para crear un Visual Basic proxy .net con un espacio de nombres de **webdata. DSSample** y almacenarlo en el archivo Sample. VB.</span><span class="sxs-lookup"><span data-stu-id="5fc41-129">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="5fc41-130">Para crear un proxy de C# en el archivo sample.cs, hay que utilizar el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fc41-130">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="5fc41-131">El proxy puede compilarse como una biblioteca e importarse en el cliente del servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="5fc41-131">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="5fc41-132">Para compilar el código de proxy de Visual Basic .NET almacenado en sample.vb como sample.dll, hay que utilizar el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="5fc41-132">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="5fc41-133">Para compilar el código de proxy de C# almacenado en sample.cs como sample.dll, hay que utilizar el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="5fc41-133">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="5fc41-134">Cree un cliente de servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="5fc41-134">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="5fc41-135">Si desea que Visual Studio genere la clase de proxy de servicio Web automáticamente, simplemente cree el proyecto de cliente y, en la ventana de explorador de soluciones, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar**  >  **referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="5fc41-135">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, and then select **Add** > **Service Reference**.</span></span> <span data-ttu-id="5fc41-136">En el cuadro de diálogo **Agregar referencia de servicio** , seleccione **avanzadas**y, a continuación, seleccione **Agregar referencia Web**.</span><span class="sxs-lookup"><span data-stu-id="5fc41-136">In the **Add Service Reference** dialog box, select **Advanced**, and then select **Add Web Reference**.</span></span> <span data-ttu-id="5fc41-137">Seleccione el servicio Web en la lista de servicios web disponibles (esto puede requerir que se proporcione la dirección del extremo de servicio Web si el servicio Web no está disponible en la solución actual o en el equipo actual).</span><span class="sxs-lookup"><span data-stu-id="5fc41-137">Select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint if the Web service isn't available within the current solution or on the current computer).</span></span> <span data-ttu-id="5fc41-138">Si crea el proxy del servicio Web XML personalmente, tal y como se describe en el paso anterior, puede importarlo en el código de cliente y utilizar los métodos de servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="5fc41-138">If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span>

     <span data-ttu-id="5fc41-139">En el código de ejemplo siguiente se importa la biblioteca de proxy, se llama a **GetCustomers** para obtener una lista de clientes, se agrega un nuevo cliente y, a continuación, se devuelve un **conjunto** de elementos con las actualizaciones a **UpdateCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5fc41-139">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="5fc41-140">En el ejemplo se pasa el **conjunto** de resultados devuelto por **DataSet. GetChanges** a **UpdateCustomers** porque solo es necesario pasar las filas modificadas a **UpdateCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5fc41-140">The example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="5fc41-141">**UpdateCustomers** devuelve el **conjunto**de datos resuelto, que se puede **combinar** en el **conjunto** de datos existente para incorporar los cambios resueltos y cualquier información de error de fila de la actualización.</span><span class="sxs-lookup"><span data-stu-id="5fc41-141">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="5fc41-142">En el código siguiente se supone que ha utilizado Visual Studio para crear la referencia Web y que ha cambiado el nombre de la referencia Web a DsSample en el cuadro de diálogo **Agregar referencia Web** .</span><span class="sxs-lookup"><span data-stu-id="5fc41-142">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
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
  
     <span data-ttu-id="5fc41-143">Si decide crear la clase de proxy personalmente, debe seguir los pasos adicionales que se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="5fc41-143">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="5fc41-144">Para compilar el ejemplo, indique la biblioteca de proxy creada (sample.dll) y las bibliotecas de .NET relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5fc41-144">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="5fc41-145">Para compilar la versión de Visual Basic .NET del ejemplo, almacenada en el archivo client.vb, hay que utilizar el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fc41-145">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="5fc41-146">Para compilar la versión de C# del ejemplo, almacenada en el archivo client.cs, hay que utilizar el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fc41-146">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5fc41-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fc41-147">See also</span></span>

- [<span data-ttu-id="5fc41-148">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5fc41-148">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="5fc41-149">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="5fc41-149">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="5fc41-150">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="5fc41-150">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="5fc41-151">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="5fc41-151">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="5fc41-152">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="5fc41-152">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="5fc41-153">Parámetros de DataAdapter</span><span class="sxs-lookup"><span data-stu-id="5fc41-153">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- <span data-ttu-id="5fc41-154">[Herramienta lenguaje de descripción de servicios web (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5fc41-154">[Web Services Description Language Tool (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="5fc41-155">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5fc41-155">ADO.NET Overview</span></span>](../ado-net-overview.md)
