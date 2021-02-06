---
description: Obtener más información acerca de cómo realizar una consulta XPath en un conjunto de información
title: Realizar una consulta XPath en un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 9febcc545f86f048b2d693f8aa6558a1b7883a60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651722"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Realizar una consulta XPath en un objeto DataSet

La relación entre un sincronizado <xref:System.Data.DataSet> y <xref:System.Xml.XmlDataDocument> permite hacer uso de servicios XML, como la consulta XPath (lenguaje de rutas XML), que tienen acceso al **XmlDataDocument** y pueden realizar determinada funcionalidad de forma más cómoda que el acceso directo al **conjunto de DataSet** . Por ejemplo, en lugar de usar el método **Select** de <xref:System.Data.DataTable> para navegar por las relaciones con otras tablas de un **DataSet**, puede realizar una consulta XPath en un **XmlDataDocument** que esté sincronizado con el **DataSet** para obtener una lista de elementos XML en forma de <xref:System.Xml.XmlNodeList> . Los nodos de la **XmlNodeList**, convertidos como <xref:System.Xml.XmlElement> nodos, se pueden pasar al método **GetRowFromElement** de **XmlDataDocument** para devolver las referencias coincidentes <xref:System.Data.DataRow> a las filas de la tabla en el **conjunto** de resultados sincronizado.  
  
 Por ejemplo, en el siguiente ejemplo de código se realiza una consulta "secundaria" de XPath. El **conjunto de DataSet** se rellena con tres tablas: **Customers**, **Orders** y **OrderDetails**. En el ejemplo, primero se crea una relación de elementos primarios y secundarios entre las tablas **Customers** y **Orders** , y entre las tablas **Orders** y **OrderDetails** . Después, se realiza una consulta XPath para devolver una **XmlNodeList** de nodos **Customers** en la que un nodo de **OrderDetails** secundario tiene un nodo **ProductID** con el valor de 43. En esencia, el ejemplo utiliza la consulta XPath para determinar qué clientes han pedido el producto que tiene el **ProductID** de 43.  
  
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
  
## <a name="see-also"></a>Vea también

- [Sincronización de DataSet y XmlDataDocument](dataset-and-xmldatadocument-synchronization.md)
- [Información general de ADO.NET](../ado-net-overview.md)
