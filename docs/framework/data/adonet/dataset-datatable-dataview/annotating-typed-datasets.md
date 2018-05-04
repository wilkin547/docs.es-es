---
title: Comentar conjuntos de datos con tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 1974ac71e367203b8b94375e43d4fde13f2df51f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="annotating-typed-datasets"></a>Comentar conjuntos de datos con tipo
Las anotaciones permiten modificar los nombres de los elementos del <xref:System.Data.DataSet> con información de tipos sin modificar el esquema subyacente. Modificación de los nombres de los elementos del esquema subyacente haría que el tipo **conjunto de datos** para hacer referencia a objetos que no existen en el origen de datos, así como perder una referencia a los objetos que existen en el origen de datos.  
  
 Con las anotaciones, puede personalizar los nombres de objetos con información de tipos **conjunto de datos** con nombres más significativos, la realización código sea más legible y con información de tipos **conjunto de datos** más fácil para los clientes que usen, dejando esquema subyacente intacto. Por ejemplo, el siguiente elemento de esquema para el **clientes** tabla de la **Northwind** base de datos, se crearán un **DataRow** nombre de objeto del  **CustomersRow** y un <xref:System.Data.DataRowCollection> denominado **clientes**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 A **DataRowCollection** nombre de **clientes** es significativo en el código de cliente, pero una **DataRow** nombre de **CustomersRow** es erróneo Dado que se trata de un único objeto. Además, en común los escenarios, el objeto se haría referencia sin el **fila** identificador y en su lugar se haría referencia al mismo simplemente como un **cliente** objeto. La solución consiste en anotar el esquema e identificar nuevos nombres para el **DataRow** y **DataRowCollection** objetos. A continuación se muestra la versión anotada del esquema anterior.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Especificar un **typedName** valo **cliente** dará como resultado un **DataRow** nombre de objeto del **cliente**. Especificar un **Customers** valo **clientes** conserva la **DataRowCollection** nombre de **clientes**.  
  
 En la siguiente tabla se muestran las anotaciones disponibles.  
  
|Anotación|Descripción|  
|----------------|-----------------|  
|**typedName**|Nombre del objeto.|  
|**Customers**|Nombre de una colección de objetos.|  
|**typedParent**|Nombre del objeto cuando se hace referencia al mismo en una relación primaria.|  
|**typedChildren**|Nombre del método para devolver objetos de una relación secundaria.|  
|**nullValue**|El valor si el valor subyacente es **DBNull**. Consulte la tabla siguiente para **nullValue** anotaciones. El valor predeterminado es **_throw**.|  
  
 En la tabla siguiente se muestra los valores que se pueden especificar para el **nullValue** anotación.  
  
|Valor nullValue|Descripción|  
|---------------------|-----------------|  
|*Valor de reemplazo*|Especifica un valor que se va a devolver. El valor devuelto debe coincidir con el tipo del elemento. Por ejemplo, utilice `nullValue="0"` para devolver 0 en el caso de campos null integer.|  
|**_throw**|Iniciar una excepción. Este es el valor predeterminado.|  
|**_null**|Devuelve una referencia nula o inicia una excepción si se encuentra un tipo primitivo.|  
|**_empty**|Cadenas, devuelve **String.Empty**, en caso contrario, devuelve un objeto creado desde un constructor vacío. Si se encuentra un tipo primitivo, inicia una excepción.|  
  
 La siguiente tabla muestra los valores predeterminados para los objetos en un tipo **conjunto de datos** y las anotaciones disponibles.  
  
|Objeto/Método/Evento|Default|Anotación|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** métodos|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**dataRow**|TableNameRow|typedName|  
|**Objeto DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Property**|PropertyName|typedName|  
|**Secundario** descriptor de acceso|GetChildTableNameRows|typedChildren|  
|**Elemento primario** descriptor de acceso|TableNameRow|typedParent|  
|**Conjunto de datos** eventos|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Para usar con un tipo **conjunto de datos** anotaciones, debe incluir la siguiente **xmlns** referencia en el esquema de lenguaje (XSD) de definición de esquemas XML. (Para crear un xsd a partir de tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con conjuntos de datos en Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Éste es un ejemplo de esquema anotado que expone la **clientes** tabla de la **Northwind** base de datos con una relación con la **pedidos** tabla incluida.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"   
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
  
 En el ejemplo de código siguiente se usa un fuertemente tipado **conjunto de datos** creado a partir del esquema de ejemplo. Utiliza un <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la **clientes** tabla y otra <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la **pedidos** tabla. Fuertemente tipado **conjunto de datos** define la **DataRelations**.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [Objetos DataSet con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
