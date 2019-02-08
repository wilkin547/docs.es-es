---
title: Comentar conjuntos de datos con tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 115960c076e8bf1692bcd4bd158407e719608740
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825737"
---
# <a name="annotating-typed-datasets"></a>Comentar conjuntos de datos con tipo
Las anotaciones permiten modificar los nombres de los elementos del <xref:System.Data.DataSet> con información de tipos sin modificar el esquema subyacente. Modificación de los nombres de los elementos de esquema subyacente haría que el objeto **DataSet** para hacer referencia a objetos que no existen en el origen de datos, así como perder una referencia a los objetos que existen en el origen de datos.  
  
 Uso de anotaciones, puede personalizar los nombres de objetos con información de tipos **conjunto de datos** con nombres más descriptivos, que el código más legible y su tipo **conjunto de datos** más fácil para los clientes usen, dejando esquema subyacente intacto. Por ejemplo, el siguiente elemento de esquema para el **clientes** tabla de la **Northwind** daría lugar a base de datos en un **DataRow** nombre de objeto de  **CustomersRow** y un <xref:System.Data.DataRowCollection> denominado **clientes**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Un **DataRowCollection** nombre de **clientes** es significativo en el código de cliente, pero un **DataRow** nombre de **CustomersRow** se presta a confusión porque es un único objeto. Además, en común los escenarios, el objeto se haría referencia sin el **fila** identificador y en su lugar se haría referencia al mismo simplemente como un **cliente** objeto. La solución consiste en anotar el esquema e identificar nuevos nombres para el **DataRow** y **DataRowCollection** objetos. A continuación se muestra la versión anotada del esquema anterior.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Especificar un **typedName** valor **cliente** dará como resultado un **DataRow** nombre de objeto de **cliente**. Especificar un **Customers** valor de **clientes** conserva la **DataRowCollection** nombre de **clientes**.  
  
 En la siguiente tabla se muestran las anotaciones disponibles.  
  
|Anotación|Descripción|  
|----------------|-----------------|  
|**typedName**|Nombre del objeto.|  
|**typedPlural**|Nombre de una colección de objetos.|  
|**typedParent**|Nombre del objeto cuando se hace referencia al mismo en una relación primaria.|  
|**typedChildren**|Nombre del método para devolver objetos de una relación secundaria.|  
|**nullValue**|El valor si el valor subyacente es **DBNull**. Consulte la tabla siguiente para **nullValue** anotaciones. El valor predeterminado es **_throw**.|  
  
 En la tabla siguiente se muestra los valores que se pueden especificar para el **nullValue** anotación.  
  
|Valor nullValue|Descripción|  
|---------------------|-----------------|  
|*Valor de reemplazo*|Especifica un valor que se va a devolver. El valor devuelto debe coincidir con el tipo del elemento. Por ejemplo, utilice `nullValue="0"` para devolver 0 en el caso de campos null integer.|  
|**_throw**|Iniciar una excepción. Este es el valor predeterminado.|  
|**_null**|Devuelve una referencia nula o inicia una excepción si se encuentra un tipo primitivo.|  
|**_empty**|Para las cadenas, devolver **String.Empty**, en caso contrario, devuelve un objeto creado desde un constructor vacío. Si se encuentra un tipo primitivo, inicia una excepción.|  
  
 La siguiente tabla muestra los valores predeterminados para los objetos en un tipo **DataSet** y las anotaciones disponibles.  
  
|Objeto/Método/Evento|Default|Anotación|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** métodos|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Property**|PropertyName|typedName|  
|**Secundarios** descriptor de acceso|GetChildTableNameRows|typedChildren|  
|**Elemento primario** descriptor de acceso|TableNameRow|typedParent|  
|**Conjunto de datos** eventos|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Para usar con el tipo **DataSet** anotaciones, debe incluir la siguiente **xmlns** referencia en el esquema de lenguaje (XSD) de definición de esquemas XML. Para crear un xsd a partir de las tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con objetos DataSet en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 El siguiente es un ejemplo de esquema anotado que expone el **clientes** tabla de la **Northwind** base de datos con una relación con el **pedidos** tabla incluida.  
  
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
  
 El siguiente ejemplo de código usa fuertemente tipado **DataSet** creado a partir del esquema de ejemplo. Utiliza una <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar el **clientes** tabla y otra <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar el **pedidos** tabla. Fuertemente tipado **DataSet** define la **DataRelations**.  
  
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
    customers.Customers.NewCustomer()  
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
    customers.Customers.NewCustomer();  
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
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Objetos DataSet con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
