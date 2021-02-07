---
description: 'Más información sobre: anotar conjuntos de DataSet con tipo'
title: Comentar conjuntos de datos con tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 6f5838e94d88fd6c9b3a1991d4c8023d5892b784
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739708"
---
# <a name="annotating-typed-datasets"></a>Comentar conjuntos de datos con tipo

Las anotaciones permiten modificar los nombres de los elementos del <xref:System.Data.DataSet> con información de tipos sin modificar el esquema subyacente. La modificación de los nombres de los elementos del esquema subyacente haría que el **conjunto** de datos con tipo hiciera referencia a objetos que no existen en el origen de datos, así como a perder una referencia a los objetos que existen en el origen de datos.  
  
 Con las anotaciones, puede personalizar los nombres de los objetos en el conjunto de **DataSet** con tipo con nombres más significativos, lo que hace que el código sea más legible y que el **conjunto** de los clientes con información sea más fácil de usar, a la vez que deja intacto el esquema subyacente. Por ejemplo, el siguiente elemento de esquema para la tabla **Customers** de la base de datos **Northwind** daría como resultado un nombre de objeto **DataRow** de **CustomersRow** y un <xref:System.Data.DataRowCollection> denominado **Customers**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 El nombre de una **DataRowCollection** de **clientes** es significativo en el código de cliente, pero un nombre de **DataRow** de **CustomersRow** es engañoso porque es un único objeto. Además, en escenarios comunes, el objeto se denominaría sin el identificador de **fila** y, en su lugar, simplemente se denominaría objeto de **cliente** . La solución es anotar el esquema e identificar los nuevos nombres para los objetos **DataRow** y **DataRowCollection** . A continuación se muestra la versión anotada del esquema anterior.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Si se especifica un valor **typedName** de **Customer** , se obtendrá un nombre de objeto **DataRow** de **Customer**. Al especificar un valor de **typedPlural** de **los clientes** , se conserva el nombre de la **DataRowCollection** de **los clientes**.  
  
 En la siguiente tabla se muestran las anotaciones disponibles.  
  
|Anotación|Descripción|  
|----------------|-----------------|  
|**typedName**|Nombre del objeto.|  
|**typedPlural**|Nombre de una colección de objetos.|  
|**typedParent**|Nombre del objeto cuando se hace referencia al mismo en una relación primaria.|  
|**typedChildren**|Nombre del método para devolver objetos de una relación secundaria.|  
|**nullValue**|Valor si el valor subyacente es **DBNull**. Vea la tabla siguiente para obtener las anotaciones **nullValue** . El valor predeterminado es **_throw**.|  
  
 En la tabla siguiente se muestran los valores que se pueden especificar para la anotación **nullValue** .  
  
|Valor nullValue|Descripción|  
|---------------------|-----------------|  
|*Valor de reemplazo*|Especifica un valor que se va a devolver. El valor devuelto debe coincidir con el tipo del elemento. Por ejemplo, utilice `nullValue="0"` para devolver 0 en el caso de campos null integer.|  
|**_throw**|Iniciar una excepción. Este es el valor predeterminado.|  
|**_null**|Devuelve una referencia nula o inicia una excepción si se encuentra un tipo primitivo.|  
|**_empty**|En el caso de las cadenas, devuelve **String. Empty**; de lo contrario, devuelve un objeto creado a partir de un constructor vacío. Si se encuentra un tipo primitivo, inicia una excepción.|  
  
 En la tabla siguiente se muestran los valores predeterminados de los objetos de un conjunto de un **DataSet** con tipo y las anotaciones disponibles.  
  
|Objeto/Método/Evento|Valor predeterminado|Anotación|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** Modalidades|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**Fila**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Propiedad**|PropertyName|typedName|  
|**Elemento secundario** Acceso|GetChildTableNameRows|typedChildren|  
|**Elemento primario** Acceso|TableNameRow|typedParent|  
|**Conjunto** de Ceso|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Para utilizar anotaciones de **conjunto** de los tipos, debe incluir la siguiente referencia **xmlns** en el esquema del lenguaje de definición de esquemas XML (XSD). Para crear un XSD a partir de tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con conjuntos de datos en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 A continuación se muestra un esquema anotado de ejemplo que expone la tabla **Customers** de la base de datos **Northwind** con una relación con la tabla **Orders** incluida.  
  
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
  
 En el ejemplo de código siguiente se utiliza un **conjunto** de un DataSet fuertemente tipado creado a partir del esquema de ejemplo. Usa una <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la tabla **Customers** y otra <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la tabla **Orders** . El **DataSet** fuertemente tipado define los objetos **DataRelation**.  
  
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
- [Objetos DataSet con tipo](typed-datasets.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
