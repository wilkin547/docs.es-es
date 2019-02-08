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
# <a name="annotating-typed-datasets"></a><span data-ttu-id="2675d-102">Comentar conjuntos de datos con tipo</span><span class="sxs-lookup"><span data-stu-id="2675d-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="2675d-103">Las anotaciones permiten modificar los nombres de los elementos del <xref:System.Data.DataSet> con información de tipos sin modificar el esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="2675d-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="2675d-104">Modificación de los nombres de los elementos de esquema subyacente haría que el objeto **DataSet** para hacer referencia a objetos que no existen en el origen de datos, así como perder una referencia a los objetos que existen en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2675d-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="2675d-105">Uso de anotaciones, puede personalizar los nombres de objetos con información de tipos **conjunto de datos** con nombres más descriptivos, que el código más legible y su tipo **conjunto de datos** más fácil para los clientes usen, dejando esquema subyacente intacto.</span><span class="sxs-lookup"><span data-stu-id="2675d-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="2675d-106">Por ejemplo, el siguiente elemento de esquema para el **clientes** tabla de la **Northwind** daría lugar a base de datos en un **DataRow** nombre de objeto de  **CustomersRow** y un <xref:System.Data.DataRowCollection> denominado **clientes**.</span><span class="sxs-lookup"><span data-stu-id="2675d-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="2675d-107">Un **DataRowCollection** nombre de **clientes** es significativo en el código de cliente, pero un **DataRow** nombre de **CustomersRow** se presta a confusión porque es un único objeto.</span><span class="sxs-lookup"><span data-stu-id="2675d-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="2675d-108">Además, en común los escenarios, el objeto se haría referencia sin el **fila** identificador y en su lugar se haría referencia al mismo simplemente como un **cliente** objeto.</span><span class="sxs-lookup"><span data-stu-id="2675d-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="2675d-109">La solución consiste en anotar el esquema e identificar nuevos nombres para el **DataRow** y **DataRowCollection** objetos.</span><span class="sxs-lookup"><span data-stu-id="2675d-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="2675d-110">A continuación se muestra la versión anotada del esquema anterior.</span><span class="sxs-lookup"><span data-stu-id="2675d-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="2675d-111">Especificar un **typedName** valor **cliente** dará como resultado un **DataRow** nombre de objeto de **cliente**.</span><span class="sxs-lookup"><span data-stu-id="2675d-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="2675d-112">Especificar un **Customers** valor de **clientes** conserva la **DataRowCollection** nombre de **clientes**.</span><span class="sxs-lookup"><span data-stu-id="2675d-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="2675d-113">En la siguiente tabla se muestran las anotaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="2675d-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="2675d-114">Anotación</span><span class="sxs-lookup"><span data-stu-id="2675d-114">Annotation</span></span>|<span data-ttu-id="2675d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2675d-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="2675d-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="2675d-116">**typedName**</span></span>|<span data-ttu-id="2675d-117">Nombre del objeto.</span><span class="sxs-lookup"><span data-stu-id="2675d-117">Name of the object.</span></span>|  
|<span data-ttu-id="2675d-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="2675d-118">**typedPlural**</span></span>|<span data-ttu-id="2675d-119">Nombre de una colección de objetos.</span><span class="sxs-lookup"><span data-stu-id="2675d-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="2675d-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="2675d-120">**typedParent**</span></span>|<span data-ttu-id="2675d-121">Nombre del objeto cuando se hace referencia al mismo en una relación primaria.</span><span class="sxs-lookup"><span data-stu-id="2675d-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="2675d-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="2675d-122">**typedChildren**</span></span>|<span data-ttu-id="2675d-123">Nombre del método para devolver objetos de una relación secundaria.</span><span class="sxs-lookup"><span data-stu-id="2675d-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="2675d-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="2675d-124">**nullValue**</span></span>|<span data-ttu-id="2675d-125">El valor si el valor subyacente es **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="2675d-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="2675d-126">Consulte la tabla siguiente para **nullValue** anotaciones.</span><span class="sxs-lookup"><span data-stu-id="2675d-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="2675d-127">El valor predeterminado es **_throw**.</span><span class="sxs-lookup"><span data-stu-id="2675d-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="2675d-128">En la tabla siguiente se muestra los valores que se pueden especificar para el **nullValue** anotación.</span><span class="sxs-lookup"><span data-stu-id="2675d-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="2675d-129">Valor nullValue</span><span class="sxs-lookup"><span data-stu-id="2675d-129">nullValue Value</span></span>|<span data-ttu-id="2675d-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="2675d-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="2675d-131">*Valor de reemplazo*</span><span class="sxs-lookup"><span data-stu-id="2675d-131">*Replacement Value*</span></span>|<span data-ttu-id="2675d-132">Especifica un valor que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="2675d-132">Specify a value to be returned.</span></span> <span data-ttu-id="2675d-133">El valor devuelto debe coincidir con el tipo del elemento.</span><span class="sxs-lookup"><span data-stu-id="2675d-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="2675d-134">Por ejemplo, utilice `nullValue="0"` para devolver 0 en el caso de campos null integer.</span><span class="sxs-lookup"><span data-stu-id="2675d-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="2675d-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="2675d-135">**_throw**</span></span>|<span data-ttu-id="2675d-136">Iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="2675d-136">Throw an exception.</span></span> <span data-ttu-id="2675d-137">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2675d-137">This is the default.</span></span>|  
|<span data-ttu-id="2675d-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="2675d-138">**_null**</span></span>|<span data-ttu-id="2675d-139">Devuelve una referencia nula o inicia una excepción si se encuentra un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="2675d-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="2675d-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="2675d-140">**_empty**</span></span>|<span data-ttu-id="2675d-141">Para las cadenas, devolver **String.Empty**, en caso contrario, devuelve un objeto creado desde un constructor vacío.</span><span class="sxs-lookup"><span data-stu-id="2675d-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="2675d-142">Si se encuentra un tipo primitivo, inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="2675d-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="2675d-143">La siguiente tabla muestra los valores predeterminados para los objetos en un tipo **DataSet** y las anotaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="2675d-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="2675d-144">Objeto/Método/Evento</span><span class="sxs-lookup"><span data-stu-id="2675d-144">Object/Method/Event</span></span>|<span data-ttu-id="2675d-145">Default</span><span class="sxs-lookup"><span data-stu-id="2675d-145">Default</span></span>|<span data-ttu-id="2675d-146">Anotación</span><span class="sxs-lookup"><span data-stu-id="2675d-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="2675d-147">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="2675d-147">**DataTable**</span></span>|<span data-ttu-id="2675d-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="2675d-148">TableNameDataTable</span></span>|<span data-ttu-id="2675d-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="2675d-149">typedPlural</span></span>|  
|<span data-ttu-id="2675d-150">**DataTable** métodos</span><span class="sxs-lookup"><span data-stu-id="2675d-150">**DataTable** Methods</span></span>|<span data-ttu-id="2675d-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="2675d-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="2675d-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="2675d-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="2675d-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="2675d-153">DeleteTableNameRow</span></span>|<span data-ttu-id="2675d-154">typedName</span><span class="sxs-lookup"><span data-stu-id="2675d-154">typedName</span></span>|  
|<span data-ttu-id="2675d-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="2675d-155">**DataRowCollection**</span></span>|<span data-ttu-id="2675d-156">TableName</span><span class="sxs-lookup"><span data-stu-id="2675d-156">TableName</span></span>|<span data-ttu-id="2675d-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="2675d-157">typedPlural</span></span>|  
|<span data-ttu-id="2675d-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="2675d-158">**DataRow**</span></span>|<span data-ttu-id="2675d-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="2675d-159">TableNameRow</span></span>|<span data-ttu-id="2675d-160">typedName</span><span class="sxs-lookup"><span data-stu-id="2675d-160">typedName</span></span>|  
|<span data-ttu-id="2675d-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="2675d-161">**DataColumn**</span></span>|<span data-ttu-id="2675d-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="2675d-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="2675d-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="2675d-163">DataRow.ColumnName</span></span>|<span data-ttu-id="2675d-164">typedName</span><span class="sxs-lookup"><span data-stu-id="2675d-164">typedName</span></span>|  
|<span data-ttu-id="2675d-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="2675d-165">**Property**</span></span>|<span data-ttu-id="2675d-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="2675d-166">PropertyName</span></span>|<span data-ttu-id="2675d-167">typedName</span><span class="sxs-lookup"><span data-stu-id="2675d-167">typedName</span></span>|  
|<span data-ttu-id="2675d-168">**Secundarios** descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="2675d-168">**Child** Accessor</span></span>|<span data-ttu-id="2675d-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="2675d-169">GetChildTableNameRows</span></span>|<span data-ttu-id="2675d-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="2675d-170">typedChildren</span></span>|  
|<span data-ttu-id="2675d-171">**Elemento primario** descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="2675d-171">**Parent** Accessor</span></span>|<span data-ttu-id="2675d-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="2675d-172">TableNameRow</span></span>|<span data-ttu-id="2675d-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="2675d-173">typedParent</span></span>|  
|<span data-ttu-id="2675d-174">**Conjunto de datos** eventos</span><span class="sxs-lookup"><span data-stu-id="2675d-174">**DataSet** Events</span></span>|<span data-ttu-id="2675d-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="2675d-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="2675d-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="2675d-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="2675d-177">typedName</span><span class="sxs-lookup"><span data-stu-id="2675d-177">typedName</span></span>|  
  
 <span data-ttu-id="2675d-178">Para usar con el tipo **DataSet** anotaciones, debe incluir la siguiente **xmlns** referencia en el esquema de lenguaje (XSD) de definición de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="2675d-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="2675d-179">Para crear un xsd a partir de las tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con objetos DataSet en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="2675d-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="2675d-180">El siguiente es un ejemplo de esquema anotado que expone el **clientes** tabla de la **Northwind** base de datos con una relación con el **pedidos** tabla incluida.</span><span class="sxs-lookup"><span data-stu-id="2675d-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="2675d-181">El siguiente ejemplo de código usa fuertemente tipado **DataSet** creado a partir del esquema de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2675d-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="2675d-182">Utiliza una <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar el **clientes** tabla y otra <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar el **pedidos** tabla.</span><span class="sxs-lookup"><span data-stu-id="2675d-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="2675d-183">Fuertemente tipado **DataSet** define la **DataRelations**.</span><span class="sxs-lookup"><span data-stu-id="2675d-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2675d-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="2675d-184">See also</span></span>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="2675d-185">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="2675d-185">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [<span data-ttu-id="2675d-186">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="2675d-186">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="2675d-187">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="2675d-187">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
