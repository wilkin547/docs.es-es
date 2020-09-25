---
title: Anidar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 8db75f486c7c08b6a02401af35c9edf9969f9063
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201283"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="94bdb-102">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="94bdb-102">Nesting DataRelations</span></span>

<span data-ttu-id="94bdb-103">En una representación relacional de datos, las tablas individuales contienen filas que están relacionadas entre sí por una columna o un conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="94bdb-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="94bdb-104">En el <xref:System.Data.DataSet> de ADO.NET, la relación entre tablas se implementa mediante una <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="94bdb-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="94bdb-105">Cuando se crea una **DataRelation**, las relaciones de elementos primarios y secundarios de las columnas solo se administran a través de la relación.</span><span class="sxs-lookup"><span data-stu-id="94bdb-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="94bdb-106">Las tablas y las columnas son entidades independientes.</span><span class="sxs-lookup"><span data-stu-id="94bdb-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="94bdb-107">En la representación jerárquica de los datos proporcionada por XML, las relaciones primaria-secundaria se representan mediante elementos primarios que contienen elementos secundarios anidados.</span><span class="sxs-lookup"><span data-stu-id="94bdb-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="94bdb-108">Para facilitar el anidamiento de objetos secundarios cuando un **conjunto** de datos se sincroniza con un <xref:System.Xml.XmlDataDocument> o se escribe como datos XML mediante **WriteXml**, la **DataRelation** expone una propiedad **anidada** .</span><span class="sxs-lookup"><span data-stu-id="94bdb-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="94bdb-109">Al establecer la propiedad **Nested** de una **DataRelation** en **true** , las filas secundarias de la relación se anidan dentro de la columna primaria cuando se escriben como datos XML o se sincronizan con **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="94bdb-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="94bdb-110">La propiedad **Nested** de la **DataRelation** es **false**de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="94bdb-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="94bdb-111">Por ejemplo, considere el siguiente **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="94bdb-111">For example, consider the following **DataSet**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 <span data-ttu-id="94bdb-112">Dado que la propiedad **Nested** del objeto **DataRelation** no está establecida en **true** para este **conjunto**de datos, los objetos secundarios no se anidan dentro de los elementos primarios cuando este **conjunto** de datos se representa como datos XML.</span><span class="sxs-lookup"><span data-stu-id="94bdb-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="94bdb-113">La transformación de la representación XML de un **conjunto** de datos que contiene **conjuntos**de datos relacionados con relaciones de datos no anidadas puede provocar un rendimiento lento.</span><span class="sxs-lookup"><span data-stu-id="94bdb-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="94bdb-114">Se recomienda anidar las relaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="94bdb-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="94bdb-115">Para ello, establezca la propiedad **Nested** en **true**.</span><span class="sxs-lookup"><span data-stu-id="94bdb-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="94bdb-116">A continuación, debe escribir código en la hoja de estilos XSLT que utilice expresiones de consulta XPath con jerarquía de arriba a abajo para localizar y transformar los datos.</span><span class="sxs-lookup"><span data-stu-id="94bdb-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="94bdb-117">En el ejemplo de código siguiente se muestra el resultado de llamar a **WriteXml** en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="94bdb-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 <span data-ttu-id="94bdb-118">Tenga en cuenta que los elementos **Customers** y **Orders** se muestran como elementos relacionados.</span><span class="sxs-lookup"><span data-stu-id="94bdb-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="94bdb-119">Si desea que los elementos **Orders** se muestren como elementos secundarios de sus respectivos elementos primarios, la propiedad **Nested** de la **DataRelation** deberá establecerse en **true** y agregaría lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94bdb-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="94bdb-120">En el código siguiente se muestra el aspecto que tendría la salida resultante, con los elementos **Orders** anidados dentro de sus respectivos elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="94bdb-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94bdb-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="94bdb-121">See also</span></span>

- [<span data-ttu-id="94bdb-122">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="94bdb-122">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="94bdb-123">Agregar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="94bdb-123">Adding DataRelations</span></span>](adding-datarelations.md)
- [<span data-ttu-id="94bdb-124">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="94bdb-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="94bdb-125">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="94bdb-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
