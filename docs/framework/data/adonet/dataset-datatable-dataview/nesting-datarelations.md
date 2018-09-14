---
title: Anidar objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 9255615c7786773f1d4f453b910fdccdf191721f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45617056"
---
# <a name="nesting-datarelations"></a>Anidar objetos DataRelation
En una representación relacional de datos, las tablas individuales contienen filas que están relacionadas entre sí por una columna o un conjunto de columnas. En el <xref:System.Data.DataSet> de ADO.NET, la relación entre tablas se implementa mediante una <xref:System.Data.DataRelation>. Cuando creas un **DataRelation**, las relaciones de elementos primarios y secundarios de las columnas se administran sólo mediante la relación. Las tablas y las columnas son entidades independientes. En la representación jerárquica de los datos proporcionada por XML, las relaciones primaria-secundaria se representan mediante elementos primarios que contienen elementos secundarios anidados.  
  
 Para facilitar el anidamiento de objetos secundarios cuando un **DataSet** se sincroniza con un <xref:System.Xml.XmlDataDocument> o se escribe como datos XML mediante **WriteXml**, el **DataRelation** expone un **Nested** propiedad. Establecer el **Nested** propiedad de un **DataRelation** a **true** hace que el elemento secundario de filas de la relación se anidan dentro de la columna primaria cuando se escribe como datos XML o sincronizar con un **XmlDataDocument**. El **Nested** propiedad de la **DataRelation** es **false**, de forma predeterminada.  
  
 Por ejemplo, considere la siguiente **DataSet**.  
  
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
  
 Dado que el **Nested** propiedad de la **DataRelation** objeto no está establecido en **true** para este **conjunto de datos**, los objetos secundarios no están anidados dentro de los elementos primarios cuando este **DataSet** se representa como datos XML. Transformar la representación XML de un **DataSet** que contiene relacionados **DataSet**s con relaciones de datos no anidadas puede provocar un rendimiento lento. Se recomienda anidar las relaciones de datos. Para ello, establezca el **Nested** propiedad **true**. A continuación, debe escribir código en la hoja de estilos XSLT que utilice expresiones de consulta XPath con jerarquía de arriba a abajo para localizar y transformar los datos.  
  
 En el ejemplo de código siguiente se muestra el resultado de llamar a **WriteXml** en el **DataSet**.  
  
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
  
 Tenga en cuenta que el **clientes** elemento y el **pedidos** los elementos se muestran como elementos relacionados. Si deseara el **pedidos** elementos que se muestran como elementos secundarios de sus respectivos elementos primarios, el **Nested** propiedad de la **DataRelation** deberá establecerse en **true** y debe agregar lo siguiente:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 El código siguiente muestra cómo la salida resultante sería, con el **pedidos** elementos anidados dentro de sus respectivos elementos primarios.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Agregar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
