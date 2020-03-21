---
title: Comentar conjuntos de datos con tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151525"
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="25b9f-102">Comentar conjuntos de datos con tipo</span><span class="sxs-lookup"><span data-stu-id="25b9f-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="25b9f-103">Las anotaciones permiten modificar los nombres de los elementos del <xref:System.Data.DataSet> con información de tipos sin modificar el esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="25b9f-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="25b9f-104">Modificar los nombres de los elementos del esquema subyacente haría que el **DataSet** con tipo hiciera referencia a objetos que no existen en el origen de datos, así como perder una referencia a los objetos que existen en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="25b9f-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="25b9f-105">Mediante anotaciones, puede personalizar los nombres de los objetos del conjunto de **datos** con tipo con nombres más significativos, lo que hace que el código sea más legible y el conjunto de **datos** con tipo sea más fácil de usar para los clientes, al tiempo que deja intacto el esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="25b9f-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="25b9f-106">Por ejemplo, el siguiente elemento de esquema para la tabla **Customers** de la base <xref:System.Data.DataRowCollection> de datos **Northwind** daría como resultado un nombre de objeto **DataRow** de **CustomersRow** y un nombre **Customers**.</span><span class="sxs-lookup"><span data-stu-id="25b9f-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="25b9f-107">Un **DataRowCollection** nombre de **Customers** es significativo en el código de cliente, pero un **DataRow** nombre de **CustomersRow** es engañoso porque es un único objeto.</span><span class="sxs-lookup"><span data-stu-id="25b9f-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="25b9f-108">Además, en escenarios comunes, se haría referencia al objeto sin el identificador **Row** y, en su lugar, se denominaría simplemente un objeto **Customer.**</span><span class="sxs-lookup"><span data-stu-id="25b9f-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="25b9f-109">La solución consiste en anotar el esquema e identificar nuevos nombres para el **DataRow** y **DataRowCollection** objetos.</span><span class="sxs-lookup"><span data-stu-id="25b9f-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="25b9f-110">A continuación se muestra la versión anotada del esquema anterior.</span><span class="sxs-lookup"><span data-stu-id="25b9f-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="25b9f-111">Si se especifica un valor **typedName** de **Customer,** se producirá un nombre de objeto **DataRow** de **Customer**.</span><span class="sxs-lookup"><span data-stu-id="25b9f-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="25b9f-112">Especificar un valor **TypedPlural** de **Customers** conserva el nombre **DataRowCollection** de **Customers**.</span><span class="sxs-lookup"><span data-stu-id="25b9f-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="25b9f-113">En la siguiente tabla se muestran las anotaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="25b9f-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="25b9f-114">Anotación</span><span class="sxs-lookup"><span data-stu-id="25b9f-114">Annotation</span></span>|<span data-ttu-id="25b9f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="25b9f-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="25b9f-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="25b9f-116">**typedName**</span></span>|<span data-ttu-id="25b9f-117">Nombre del objeto.</span><span class="sxs-lookup"><span data-stu-id="25b9f-117">Name of the object.</span></span>|  
|<span data-ttu-id="25b9f-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="25b9f-118">**typedPlural**</span></span>|<span data-ttu-id="25b9f-119">Nombre de una colección de objetos.</span><span class="sxs-lookup"><span data-stu-id="25b9f-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="25b9f-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="25b9f-120">**typedParent**</span></span>|<span data-ttu-id="25b9f-121">Nombre del objeto cuando se hace referencia al mismo en una relación primaria.</span><span class="sxs-lookup"><span data-stu-id="25b9f-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="25b9f-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="25b9f-122">**typedChildren**</span></span>|<span data-ttu-id="25b9f-123">Nombre del método para devolver objetos de una relación secundaria.</span><span class="sxs-lookup"><span data-stu-id="25b9f-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="25b9f-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="25b9f-124">**nullValue**</span></span>|<span data-ttu-id="25b9f-125">Valor si el valor subyacente es **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="25b9f-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="25b9f-126">Consulte la tabla siguiente para ver las anotaciones **nullValue.**</span><span class="sxs-lookup"><span data-stu-id="25b9f-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="25b9f-127">El valor predeterminado es **_throw**.</span><span class="sxs-lookup"><span data-stu-id="25b9f-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="25b9f-128">En la tabla siguiente se muestran los valores que se pueden especificar para la anotación **nullValue.**</span><span class="sxs-lookup"><span data-stu-id="25b9f-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="25b9f-129">Valor nullValue</span><span class="sxs-lookup"><span data-stu-id="25b9f-129">nullValue Value</span></span>|<span data-ttu-id="25b9f-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="25b9f-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="25b9f-131">*Valor de reemplazo*</span><span class="sxs-lookup"><span data-stu-id="25b9f-131">*Replacement Value*</span></span>|<span data-ttu-id="25b9f-132">Especifica un valor que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="25b9f-132">Specify a value to be returned.</span></span> <span data-ttu-id="25b9f-133">El valor devuelto debe coincidir con el tipo del elemento.</span><span class="sxs-lookup"><span data-stu-id="25b9f-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="25b9f-134">Por ejemplo, utilice `nullValue="0"` para devolver 0 en el caso de campos null integer.</span><span class="sxs-lookup"><span data-stu-id="25b9f-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="25b9f-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="25b9f-135">**_throw**</span></span>|<span data-ttu-id="25b9f-136">Iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="25b9f-136">Throw an exception.</span></span> <span data-ttu-id="25b9f-137">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="25b9f-137">This is the default.</span></span>|  
|<span data-ttu-id="25b9f-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="25b9f-138">**_null**</span></span>|<span data-ttu-id="25b9f-139">Devuelve una referencia nula o inicia una excepción si se encuentra un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="25b9f-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="25b9f-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="25b9f-140">**_empty**</span></span>|<span data-ttu-id="25b9f-141">Para las cadenas, devuelva **String.Empty**, de lo contrario, devuelva un objeto creado a partir de un constructor vacío.</span><span class="sxs-lookup"><span data-stu-id="25b9f-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="25b9f-142">Si se encuentra un tipo primitivo, inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="25b9f-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="25b9f-143">En la tabla siguiente se muestran los valores predeterminados de los objetos de un **dataSet** con tipo y las anotaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="25b9f-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="25b9f-144">Objeto/Método/Evento</span><span class="sxs-lookup"><span data-stu-id="25b9f-144">Object/Method/Event</span></span>|<span data-ttu-id="25b9f-145">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="25b9f-145">Default</span></span>|<span data-ttu-id="25b9f-146">Anotación</span><span class="sxs-lookup"><span data-stu-id="25b9f-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="25b9f-147">**Datatable**</span><span class="sxs-lookup"><span data-stu-id="25b9f-147">**DataTable**</span></span>|<span data-ttu-id="25b9f-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="25b9f-148">TableNameDataTable</span></span>|<span data-ttu-id="25b9f-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="25b9f-149">typedPlural</span></span>|  
|<span data-ttu-id="25b9f-150">**DataTable** Métodos</span><span class="sxs-lookup"><span data-stu-id="25b9f-150">**DataTable** Methods</span></span>|<span data-ttu-id="25b9f-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="25b9f-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="25b9f-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="25b9f-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="25b9f-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="25b9f-153">DeleteTableNameRow</span></span>|<span data-ttu-id="25b9f-154">typedName</span><span class="sxs-lookup"><span data-stu-id="25b9f-154">typedName</span></span>|  
|<span data-ttu-id="25b9f-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="25b9f-155">**DataRowCollection**</span></span>|<span data-ttu-id="25b9f-156">TableName</span><span class="sxs-lookup"><span data-stu-id="25b9f-156">TableName</span></span>|<span data-ttu-id="25b9f-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="25b9f-157">typedPlural</span></span>|  
|<span data-ttu-id="25b9f-158">**Datarow**</span><span class="sxs-lookup"><span data-stu-id="25b9f-158">**DataRow**</span></span>|<span data-ttu-id="25b9f-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="25b9f-159">TableNameRow</span></span>|<span data-ttu-id="25b9f-160">typedName</span><span class="sxs-lookup"><span data-stu-id="25b9f-160">typedName</span></span>|  
|<span data-ttu-id="25b9f-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="25b9f-161">**DataColumn**</span></span>|<span data-ttu-id="25b9f-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="25b9f-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="25b9f-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="25b9f-163">DataRow.ColumnName</span></span>|<span data-ttu-id="25b9f-164">typedName</span><span class="sxs-lookup"><span data-stu-id="25b9f-164">typedName</span></span>|  
|<span data-ttu-id="25b9f-165">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="25b9f-165">**Property**</span></span>|<span data-ttu-id="25b9f-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="25b9f-166">PropertyName</span></span>|<span data-ttu-id="25b9f-167">typedName</span><span class="sxs-lookup"><span data-stu-id="25b9f-167">typedName</span></span>|  
|<span data-ttu-id="25b9f-168">**Niño** Descriptor</span><span class="sxs-lookup"><span data-stu-id="25b9f-168">**Child** Accessor</span></span>|<span data-ttu-id="25b9f-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="25b9f-169">GetChildTableNameRows</span></span>|<span data-ttu-id="25b9f-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="25b9f-170">typedChildren</span></span>|  
|<span data-ttu-id="25b9f-171">**Padre** Descriptor</span><span class="sxs-lookup"><span data-stu-id="25b9f-171">**Parent** Accessor</span></span>|<span data-ttu-id="25b9f-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="25b9f-172">TableNameRow</span></span>|<span data-ttu-id="25b9f-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="25b9f-173">typedParent</span></span>|  
|<span data-ttu-id="25b9f-174">**DataSet** Eventos</span><span class="sxs-lookup"><span data-stu-id="25b9f-174">**DataSet** Events</span></span>|<span data-ttu-id="25b9f-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="25b9f-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="25b9f-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="25b9f-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="25b9f-177">typedName</span><span class="sxs-lookup"><span data-stu-id="25b9f-177">typedName</span></span>|  
  
 <span data-ttu-id="25b9f-178">Para usar anotaciones **DataSet** con tipo, debe incluir la siguiente referencia **xmlns** en el esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="25b9f-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="25b9f-179">Para crear un xsd a <xref:System.Data.DataSet.WriteXmlSchema%2A> partir de tablas de base de datos, vea o [Trabajar con conjuntos](/visualstudio/data-tools/dataset-tools-in-visual-studio)de datos en Visual Studio .</span><span class="sxs-lookup"><span data-stu-id="25b9f-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="25b9f-180">A continuación se muestra un esquema anotado de ejemplo que expone la tabla **Customers** de la base de datos **Northwind** con una relación con la tabla **Orders** incluida.</span><span class="sxs-lookup"><span data-stu-id="25b9f-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="25b9f-181">En el ejemplo de código siguiente se usa un **DataSet** fuertemente tipado creado a partir del esquema de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="25b9f-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="25b9f-182">Usa uno <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la <xref:System.Data.SqlClient.SqlDataAdapter> tabla **Customers** y otro para rellenar la tabla **Orders.**</span><span class="sxs-lookup"><span data-stu-id="25b9f-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="25b9f-183">El **DataSet** fuertemente tipado define **DataRelations**.</span><span class="sxs-lookup"><span data-stu-id="25b9f-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25b9f-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25b9f-184">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="25b9f-185">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="25b9f-185">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="25b9f-186">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="25b9f-186">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="25b9f-187">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="25b9f-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
