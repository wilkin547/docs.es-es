---
title: "Anotar DataSets con tipos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Anotar DataSets con tipos
Las anotaciones permiten modificar los nombres de los elementos del <xref:System.Data.DataSet> con información de tipos sin modificar el esquema subyacente.  La modificación de los nombres de los elementos del esquema subyacente haría que el **DataSet** con información de tipos hiciera referencia a objetos que no existen en el origen de datos, además de perder una referencia a los objetos existentes en el origen de datos.  
  
 Con las anotaciones es posible personalizar los nombres de objetos del **DataSet** con información de tipos para utilizar nombres más significativos; esto hace que el código sea más legible y que los clientes puedan utilizar más fácilmente el **DataSet**, al tiempo que se deja intacto el esquema subyacente.  Por ejemplo, el siguiente elemento de esquema para la tabla **Customers** de la base de datos **Northwind** da como resultado un nombre de objeto **DataRow** de **CustomersRow** y una <xref:System.Data.DataRowCollection> denominada **Customers**.  
  
```  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Un nombre **Customers** para una **DataRowCollection** es significativo en el código de cliente, pero una **DataRow** denominada **CustomersRow** puede llevar a confusión porque se trata de un único objeto.  Además, en situaciones normales, se haría referencia al objeto sin el identificador **Row** y en su lugar se haría referencia al mismo simplemente como un objeto **Customer**.  La solución consiste en anotar el esquema e identificar nuevos nombres para los objetos **DataRow** y **DataRowCollection**.  A continuación se muestra la versión anotada del esquema anterior.  
  
```  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Al especificar un valor **Customer** para **typedName**, el nombre de un objeto **DataRow** será **Customer**.  Si se especifica el valor **Customers** para **typedPlural** se conservará el nombre **Customers** para **DataRowCollection**.  
  
 En la siguiente tabla se muestran las anotaciones disponibles.  
  
|Anotación|Descripción|  
|---------------|-----------------|  
|**typedName**|Nombre del objeto.|  
|**typedPlural**|Nombre de una colección de objetos.|  
|**typedParent**|Nombre del objeto cuando se hace referencia al mismo en una relación primaria.|  
|**typedChildren**|Nombre del método para devolver objetos de una relación secundaria.|  
|**nullValue**|Valor si el valor subyacente es **DBNull**.  Vea las anotaciones **nullValue** en la tabla siguiente.  El valor predeterminado es **\_throw**.|  
  
 En la tabla siguiente se presentan los valores que se pueden especificar para la anotación **nullValue**.  
  
|Valor nullValue|Descripción|  
|---------------------|-----------------|  
|*Valor de reemplazo*|Especifica un valor que se va a devolver.  El valor devuelto debe coincidir con el tipo del elemento.  Por ejemplo, utilice `nullValue="0"` para devolver 0 en el caso de campos null integer.|  
|**\_throw**|Iniciar una excepción.  Este es el valor predeterminado.|  
|**\_null**|Devuelve una referencia nula o inicia una excepción si se encuentra un tipo primitivo.|  
|**\_empty**|En el caso de cadenas, devuelve **String.Empty**; de lo contrario, devuelve un objeto creado desde un constructor vacío.  Si se encuentra un tipo primitivo, inicia una excepción.|  
  
 En la siguiente tabla se muestran los valores predeterminados de los objetos en un **DataSet** con información de tipos y las anotaciones disponibles.  
  
|Objeto\/Método\/Evento|Default|Anotación|  
|----------------------------|-------------|---------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|Métodos **DataTable**|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Propiedad**|PropertyName|typedName|  
|Descriptor de acceso **secundario**|GetChildTableNameRows|typedChildren|  
|Descriptor de acceso **Parent**|TableNameRow|typedParent|  
|Eventos **DataSet**|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Para utilizar anotaciones de **DataSet** con información de tipos debe incluir la siguiente referencia **xmlns** en el esquema del lenguaje de definición de esquemas XML \(XSD\).  \(Para crear un xsd a partir de las tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [Trabajar con los conjuntos de datos en Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)\).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 A continuación se muestra un ejemplo de esquema anotado que expone la tabla **Customers** de la base de datos **Northwind**, incluida una relación con la tabla **Orders**.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer"  
codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone"  
codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order"  
codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"  
                 codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter"  
codegen:nullValue="1980-01-01T00:00:00"   
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 En el siguiente ejemplo de código se utiliza un **DataSet** fuertemente tipado creado a partir del esquema de ejemplo.  Utiliza un <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la tabla **Customers** y otro <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la tabla **Orders**.  El **DataSet** fuertemente tipado define las **DataRelations**.  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomeromer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",   
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new   
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =   
    customers.Customers.NewCustomeromer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## Vea también  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [DataSets con establecimiento de tipos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)