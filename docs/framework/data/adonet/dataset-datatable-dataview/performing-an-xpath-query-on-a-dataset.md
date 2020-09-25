---
title: Realizar una consulta XPath en un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: d7897815874f2e9de2f4c24d3c141d464a296b31
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201244"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="b9cae-102">Realizar una consulta XPath en un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="b9cae-102">Performing an XPath Query on a DataSet</span></span>

<span data-ttu-id="b9cae-103">La relación entre un sincronizado <xref:System.Data.DataSet> y <xref:System.Xml.XmlDataDocument> permite hacer uso de servicios XML, como la consulta XPath (lenguaje de rutas XML), que tienen acceso al **XmlDataDocument** y pueden realizar determinada funcionalidad de forma más cómoda que el acceso directo al **conjunto de DataSet** .</span><span class="sxs-lookup"><span data-stu-id="b9cae-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="b9cae-104">Por ejemplo, en lugar de usar el método **Select** de <xref:System.Data.DataTable> para navegar por las relaciones con otras tablas de un **DataSet**, puede realizar una consulta XPath en un **XmlDataDocument** que esté sincronizado con el **DataSet**para obtener una lista de elementos XML en forma de <xref:System.Xml.XmlNodeList> .</span><span class="sxs-lookup"><span data-stu-id="b9cae-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="b9cae-105">Los nodos de la **XmlNodeList**, convertidos como <xref:System.Xml.XmlElement> nodos, se pueden pasar al método **GetRowFromElement** de **XmlDataDocument**para devolver las referencias coincidentes <xref:System.Data.DataRow> a las filas de la tabla en el **conjunto**de resultados sincronizado.</span><span class="sxs-lookup"><span data-stu-id="b9cae-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="b9cae-106">Por ejemplo, en el siguiente ejemplo de código se realiza una consulta "secundaria" de XPath.</span><span class="sxs-lookup"><span data-stu-id="b9cae-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="b9cae-107">El **conjunto de DataSet** se rellena con tres tablas: **Customers**, **Orders**y **OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="b9cae-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="b9cae-108">En el ejemplo, primero se crea una relación de elementos primarios y secundarios entre las tablas **Customers** y **Orders** , y entre las tablas **Orders** y **OrderDetails** .</span><span class="sxs-lookup"><span data-stu-id="b9cae-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="b9cae-109">Después, se realiza una consulta XPath para devolver una **XmlNodeList** de nodos **Customers** en la que un nodo de **OrderDetails** secundario tiene un nodo **ProductID** con el valor de 43.</span><span class="sxs-lookup"><span data-stu-id="b9cae-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="b9cae-110">En esencia, el ejemplo utiliza la consulta XPath para determinar qué clientes han pedido el producto que tiene el **ProductID** de 43.</span><span class="sxs-lookup"><span data-stu-id="b9cae-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9cae-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9cae-111">See also</span></span>

- [<span data-ttu-id="b9cae-112">Sincronización de DataSet y XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="b9cae-112">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="b9cae-113">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9cae-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
