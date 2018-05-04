---
title: Realizar una consulta XPath en un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: c785cc69289440918f45974c711ae0b112130c5d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Realizar una consulta XPath en un objeto DataSet
La relación entre un sincronizada <xref:System.Data.DataSet> y <xref:System.Xml.XmlDataDocument> le permite hacer uso de XML servicios, como las consultas XML Path Language (XPath), que tienen acceso a la **XmlDataDocument** y puede realizar ciertas funciones más cómodamente que si tuviera acceso la **conjunto de datos** directamente. Por ejemplo, en lugar de usar el **seleccione** método de un <xref:System.Data.DataTable> para navegar por relaciones con otras tablas de un **conjunto de datos**, puede realizar una consulta XPath en un **XmlDataDocument**  que está sincronizado con el **conjunto de datos**, para obtener una lista de elementos XML en forma de un <xref:System.Xml.XmlNodeList>. Los nodos de la **XmlNodeList**, convertidos en <xref:System.Xml.XmlElement> nodos, a continuación, puede pasarse a la **GetRowFromElement** método de la **XmlDataDocument**para devolver la búsqueda de coincidencias <xref:System.Data.DataRow> referencias a las filas de la tabla en sincronizada **conjunto de datos**.  
  
 Por ejemplo, en el siguiente ejemplo de código se realiza una consulta "secundaria" de XPath. El **conjunto de datos** se rellena con tres tablas: **clientes**, **pedidos**, y **OrderDetails**. En el ejemplo, primero se crea una relación de elementos primarios y secundarios entre el **clientes** y **pedidos** tablas y entre el **pedidos** y **OrderDetails** tablas. A continuación, se realiza una consulta XPath para devolver una **XmlNodeList** de **clientes** nodos donde un secundario **OrderDetails** nodo tiene un **ProductID**nodo con el valor 43. En esencia, el ejemplo utiliza la consulta XPath para determinar qué clientes han pedido el producto que tiene el **ProductID** es 43.  
  
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
 [Sincronización de DataSet y XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
