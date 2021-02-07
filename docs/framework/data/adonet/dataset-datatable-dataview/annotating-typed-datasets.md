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
# <a name="annotating-typed-datasets"></a><span data-ttu-id="8cc5c-103">Comentar conjuntos de datos con tipo</span><span class="sxs-lookup"><span data-stu-id="8cc5c-103">Annotating Typed DataSets</span></span>

<span data-ttu-id="8cc5c-104">Las anotaciones permiten modificar los nombres de los elementos del <xref:System.Data.DataSet> con información de tipos sin modificar el esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-104">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="8cc5c-105">La modificación de los nombres de los elementos del esquema subyacente haría que el **conjunto** de datos con tipo hiciera referencia a objetos que no existen en el origen de datos, así como a perder una referencia a los objetos que existen en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-105">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="8cc5c-106">Con las anotaciones, puede personalizar los nombres de los objetos en el conjunto de **DataSet** con tipo con nombres más significativos, lo que hace que el código sea más legible y que el **conjunto** de los clientes con información sea más fácil de usar, a la vez que deja intacto el esquema subyacente.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-106">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="8cc5c-107">Por ejemplo, el siguiente elemento de esquema para la tabla **Customers** de la base de datos **Northwind** daría como resultado un nombre de objeto **DataRow** de **CustomersRow** y un <xref:System.Data.DataRowCollection> denominado **Customers**.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-107">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="8cc5c-108">El nombre de una **DataRowCollection** de **clientes** es significativo en el código de cliente, pero un nombre de **DataRow** de **CustomersRow** es engañoso porque es un único objeto.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-108">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="8cc5c-109">Además, en escenarios comunes, el objeto se denominaría sin el identificador de **fila** y, en su lugar, simplemente se denominaría objeto de **cliente** .</span><span class="sxs-lookup"><span data-stu-id="8cc5c-109">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="8cc5c-110">La solución es anotar el esquema e identificar los nuevos nombres para los objetos **DataRow** y **DataRowCollection** .</span><span class="sxs-lookup"><span data-stu-id="8cc5c-110">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="8cc5c-111">A continuación se muestra la versión anotada del esquema anterior.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-111">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="8cc5c-112">Si se especifica un valor **typedName** de **Customer** , se obtendrá un nombre de objeto **DataRow** de **Customer**.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-112">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="8cc5c-113">Al especificar un valor de **typedPlural** de **los clientes** , se conserva el nombre de la **DataRowCollection** de **los clientes**.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-113">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="8cc5c-114">En la siguiente tabla se muestran las anotaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-114">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="8cc5c-115">Anotación</span><span class="sxs-lookup"><span data-stu-id="8cc5c-115">Annotation</span></span>|<span data-ttu-id="8cc5c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cc5c-116">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="8cc5c-117">**typedName**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-117">**typedName**</span></span>|<span data-ttu-id="8cc5c-118">Nombre del objeto.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-118">Name of the object.</span></span>|  
|<span data-ttu-id="8cc5c-119">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-119">**typedPlural**</span></span>|<span data-ttu-id="8cc5c-120">Nombre de una colección de objetos.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-120">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="8cc5c-121">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-121">**typedParent**</span></span>|<span data-ttu-id="8cc5c-122">Nombre del objeto cuando se hace referencia al mismo en una relación primaria.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-122">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="8cc5c-123">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-123">**typedChildren**</span></span>|<span data-ttu-id="8cc5c-124">Nombre del método para devolver objetos de una relación secundaria.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-124">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="8cc5c-125">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-125">**nullValue**</span></span>|<span data-ttu-id="8cc5c-126">Valor si el valor subyacente es **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-126">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="8cc5c-127">Vea la tabla siguiente para obtener las anotaciones **nullValue** .</span><span class="sxs-lookup"><span data-stu-id="8cc5c-127">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="8cc5c-128">El valor predeterminado es **_throw**.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-128">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="8cc5c-129">En la tabla siguiente se muestran los valores que se pueden especificar para la anotación **nullValue** .</span><span class="sxs-lookup"><span data-stu-id="8cc5c-129">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="8cc5c-130">Valor nullValue</span><span class="sxs-lookup"><span data-stu-id="8cc5c-130">nullValue Value</span></span>|<span data-ttu-id="8cc5c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cc5c-131">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="8cc5c-132">*Valor de reemplazo*</span><span class="sxs-lookup"><span data-stu-id="8cc5c-132">*Replacement Value*</span></span>|<span data-ttu-id="8cc5c-133">Especifica un valor que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-133">Specify a value to be returned.</span></span> <span data-ttu-id="8cc5c-134">El valor devuelto debe coincidir con el tipo del elemento.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-134">The returned value must match the type of the element.</span></span> <span data-ttu-id="8cc5c-135">Por ejemplo, utilice `nullValue="0"` para devolver 0 en el caso de campos null integer.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-135">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="8cc5c-136">**_throw**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-136">**_throw**</span></span>|<span data-ttu-id="8cc5c-137">Iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-137">Throw an exception.</span></span> <span data-ttu-id="8cc5c-138">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-138">This is the default.</span></span>|  
|<span data-ttu-id="8cc5c-139">**_null**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-139">**_null**</span></span>|<span data-ttu-id="8cc5c-140">Devuelve una referencia nula o inicia una excepción si se encuentra un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-140">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="8cc5c-141">**_empty**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-141">**_empty**</span></span>|<span data-ttu-id="8cc5c-142">En el caso de las cadenas, devuelve **String. Empty**; de lo contrario, devuelve un objeto creado a partir de un constructor vacío.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-142">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="8cc5c-143">Si se encuentra un tipo primitivo, inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-143">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="8cc5c-144">En la tabla siguiente se muestran los valores predeterminados de los objetos de un conjunto de un **DataSet** con tipo y las anotaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-144">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="8cc5c-145">Objeto/Método/Evento</span><span class="sxs-lookup"><span data-stu-id="8cc5c-145">Object/Method/Event</span></span>|<span data-ttu-id="8cc5c-146">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="8cc5c-146">Default</span></span>|<span data-ttu-id="8cc5c-147">Anotación</span><span class="sxs-lookup"><span data-stu-id="8cc5c-147">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="8cc5c-148">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-148">**DataTable**</span></span>|<span data-ttu-id="8cc5c-149">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="8cc5c-149">TableNameDataTable</span></span>|<span data-ttu-id="8cc5c-150">typedPlural</span><span class="sxs-lookup"><span data-stu-id="8cc5c-150">typedPlural</span></span>|  
|<span data-ttu-id="8cc5c-151">**DataTable** Modalidades</span><span class="sxs-lookup"><span data-stu-id="8cc5c-151">**DataTable** Methods</span></span>|<span data-ttu-id="8cc5c-152">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="8cc5c-152">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="8cc5c-153">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="8cc5c-153">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="8cc5c-154">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="8cc5c-154">DeleteTableNameRow</span></span>|<span data-ttu-id="8cc5c-155">typedName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-155">typedName</span></span>|  
|<span data-ttu-id="8cc5c-156">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-156">**DataRowCollection**</span></span>|<span data-ttu-id="8cc5c-157">TableName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-157">TableName</span></span>|<span data-ttu-id="8cc5c-158">typedPlural</span><span class="sxs-lookup"><span data-stu-id="8cc5c-158">typedPlural</span></span>|  
|<span data-ttu-id="8cc5c-159">**Fila**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-159">**DataRow**</span></span>|<span data-ttu-id="8cc5c-160">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="8cc5c-160">TableNameRow</span></span>|<span data-ttu-id="8cc5c-161">typedName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-161">typedName</span></span>|  
|<span data-ttu-id="8cc5c-162">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-162">**DataColumn**</span></span>|<span data-ttu-id="8cc5c-163">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="8cc5c-163">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="8cc5c-164">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-164">DataRow.ColumnName</span></span>|<span data-ttu-id="8cc5c-165">typedName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-165">typedName</span></span>|  
|<span data-ttu-id="8cc5c-166">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="8cc5c-166">**Property**</span></span>|<span data-ttu-id="8cc5c-167">PropertyName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-167">PropertyName</span></span>|<span data-ttu-id="8cc5c-168">typedName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-168">typedName</span></span>|  
|<span data-ttu-id="8cc5c-169">**Elemento secundario** Acceso</span><span class="sxs-lookup"><span data-stu-id="8cc5c-169">**Child** Accessor</span></span>|<span data-ttu-id="8cc5c-170">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="8cc5c-170">GetChildTableNameRows</span></span>|<span data-ttu-id="8cc5c-171">typedChildren</span><span class="sxs-lookup"><span data-stu-id="8cc5c-171">typedChildren</span></span>|  
|<span data-ttu-id="8cc5c-172">**Elemento primario** Acceso</span><span class="sxs-lookup"><span data-stu-id="8cc5c-172">**Parent** Accessor</span></span>|<span data-ttu-id="8cc5c-173">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="8cc5c-173">TableNameRow</span></span>|<span data-ttu-id="8cc5c-174">typedParent</span><span class="sxs-lookup"><span data-stu-id="8cc5c-174">typedParent</span></span>|  
|<span data-ttu-id="8cc5c-175">**Conjunto** de Ceso</span><span class="sxs-lookup"><span data-stu-id="8cc5c-175">**DataSet** Events</span></span>|<span data-ttu-id="8cc5c-176">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="8cc5c-176">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="8cc5c-177">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="8cc5c-177">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="8cc5c-178">typedName</span><span class="sxs-lookup"><span data-stu-id="8cc5c-178">typedName</span></span>|  
  
 <span data-ttu-id="8cc5c-179">Para utilizar anotaciones de **conjunto** de los tipos, debe incluir la siguiente referencia **xmlns** en el esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="8cc5c-179">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="8cc5c-180">Para crear un XSD a partir de tablas de base de datos, vea <xref:System.Data.DataSet.WriteXmlSchema%2A> o [trabajar con conjuntos de datos en Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="8cc5c-180">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="8cc5c-181">A continuación se muestra un esquema anotado de ejemplo que expone la tabla **Customers** de la base de datos **Northwind** con una relación con la tabla **Orders** incluida.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-181">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="8cc5c-182">En el ejemplo de código siguiente se utiliza un **conjunto** de un DataSet fuertemente tipado creado a partir del esquema de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-182">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="8cc5c-183">Usa una <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la tabla **Customers** y otra <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar la tabla **Orders** .</span><span class="sxs-lookup"><span data-stu-id="8cc5c-183">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="8cc5c-184">El **DataSet** fuertemente tipado define los objetos **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="8cc5c-184">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8cc5c-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cc5c-185">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="8cc5c-186">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="8cc5c-186">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="8cc5c-187">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="8cc5c-187">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="8cc5c-188">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8cc5c-188">ADO.NET Overview</span></span>](../ado-net-overview.md)
