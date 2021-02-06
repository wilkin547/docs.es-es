---
description: Más información acerca de cómo anidar objetos DataRelation
title: Anidar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: d998802a11fbb2bf414aa28b4beee95cac70a819
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651761"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="deab0-103">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="deab0-103">Nesting DataRelations</span></span>

<span data-ttu-id="deab0-104">En una representación relacional de datos, las tablas individuales contienen filas que están relacionadas entre sí por una columna o un conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="deab0-104">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="deab0-105">En el <xref:System.Data.DataSet> de ADO.NET, la relación entre tablas se implementa mediante una <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="deab0-105">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="deab0-106">Cuando se crea una **DataRelation**, las relaciones de elementos primarios y secundarios de las columnas solo se administran a través de la relación.</span><span class="sxs-lookup"><span data-stu-id="deab0-106">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="deab0-107">Las tablas y las columnas son entidades independientes.</span><span class="sxs-lookup"><span data-stu-id="deab0-107">The tables and columns are separate entities.</span></span> <span data-ttu-id="deab0-108">En la representación jerárquica de los datos proporcionada por XML, las relaciones primaria-secundaria se representan mediante elementos primarios que contienen elementos secundarios anidados.</span><span class="sxs-lookup"><span data-stu-id="deab0-108">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="deab0-109">Para facilitar el anidamiento de objetos secundarios cuando un **conjunto** de datos se sincroniza con un <xref:System.Xml.XmlDataDocument> o se escribe como datos XML mediante **WriteXml**, la **DataRelation** expone una propiedad **anidada** .</span><span class="sxs-lookup"><span data-stu-id="deab0-109">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="deab0-110">Al establecer la propiedad **Nested** de una **DataRelation** en **true** , las filas secundarias de la relación se anidan dentro de la columna primaria cuando se escriben como datos XML o se sincronizan con **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="deab0-110">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="deab0-111">La propiedad **Nested** de la **DataRelation** es **false** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="deab0-111">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="deab0-112">Por ejemplo, considere el siguiente **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="deab0-112">For example, consider the following **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="deab0-113">Dado que la propiedad **Nested** del objeto **DataRelation** no está establecida en **true** para este **conjunto** de datos, los objetos secundarios no se anidan dentro de los elementos primarios cuando este **conjunto** de datos se representa como datos XML.</span><span class="sxs-lookup"><span data-stu-id="deab0-113">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="deab0-114">La transformación de la representación XML de un **conjunto** de datos que contiene **conjuntos** de datos relacionados con relaciones de datos no anidadas puede provocar un rendimiento lento.</span><span class="sxs-lookup"><span data-stu-id="deab0-114">Transforming the XML representation of a **DataSet** that contains related **DataSet** s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="deab0-115">Se recomienda anidar las relaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="deab0-115">We recommend that you nest the data relations.</span></span> <span data-ttu-id="deab0-116">Para ello, establezca la propiedad **Nested** en **true**.</span><span class="sxs-lookup"><span data-stu-id="deab0-116">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="deab0-117">A continuación, debe escribir código en la hoja de estilos XSLT que utilice expresiones de consulta XPath con jerarquía de arriba a abajo para localizar y transformar los datos.</span><span class="sxs-lookup"><span data-stu-id="deab0-117">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="deab0-118">En el ejemplo de código siguiente se muestra el resultado de llamar a **WriteXml** en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="deab0-118">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="deab0-119">Tenga en cuenta que los elementos **Customers** y **Orders** se muestran como elementos relacionados.</span><span class="sxs-lookup"><span data-stu-id="deab0-119">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="deab0-120">Si desea que los elementos **Orders** se muestren como elementos secundarios de sus respectivos elementos primarios, la propiedad **Nested** de la **DataRelation** deberá establecerse en **true** y agregaría lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="deab0-120">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="deab0-121">En el código siguiente se muestra el aspecto que tendría la salida resultante, con los elementos **Orders** anidados dentro de sus respectivos elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="deab0-121">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="deab0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="deab0-122">See also</span></span>

- [<span data-ttu-id="deab0-123">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="deab0-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="deab0-124">Agregar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="deab0-124">Adding DataRelations</span></span>](adding-datarelations.md)
- [<span data-ttu-id="deab0-125">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="deab0-125">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="deab0-126">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="deab0-126">ADO.NET Overview</span></span>](../ado-net-overview.md)
