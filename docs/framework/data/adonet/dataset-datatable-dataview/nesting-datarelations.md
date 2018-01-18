---
title: Anidar objetos DataRelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c057e836e8903fc2f5cb28f74858be97d2ffcc14
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="nesting-datarelations"></a>Anidar objetos DataRelation
En una representación relacional de datos, las tablas individuales contienen filas que están relacionadas entre sí por una columna o un conjunto de columnas. En el <xref:System.Data.DataSet> de ADO.NET, la relación entre tablas se implementa mediante una <xref:System.Data.DataRelation>. Cuando se crea un **DataRelation**, las relaciones de elementos primarios y secundarios de las columnas se administran sólo mediante la relación. Las tablas y las columnas son entidades independientes. En la representación jerárquica de los datos proporcionada por XML, las relaciones primaria-secundaria se representan mediante elementos primarios que contienen elementos secundarios anidados.  
  
 Para facilitar el anidamiento de objetos secundarios cuando un **conjunto de datos** está sincronizado con un <xref:System.Xml.XmlDataDocument> o se escribe como datos XML mediante **WriteXml**, **DataRelation** expone un **Nested** propiedad. Establecer el **Nested** propiedad de un **DataRelation** a **true** , las filas de la relación se anidan dentro de la columna primaria cuando se escriben como datos XML secundarias o sincronizar con un **XmlDataDocument**. El **Nested** propiedad de la **DataRelation** es **false**, de forma predeterminada.  
  
 Por ejemplo, considere el siguiente **conjunto de datos**.  
  
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
  
 Dado que la **Nested** propiedad de la **DataRelation** objeto no está establecido en **true** para este **conjunto de datos**, los objetos secundarios no están anidados dentro de los elementos primarios cuando este **conjunto de datos** se representa como datos XML. Transformar la representación XML de un **conjunto de datos** que contiene relacionados **conjunto de datos**con relaciones de datos no anidadas puede provocar un rendimiento lento. Se recomienda anidar las relaciones de datos. Para ello, establezca la **Nested** propiedad **true**. A continuación, debe escribir código en la hoja de estilos XSLT que utilice expresiones de consulta XPath con jerarquía de arriba a abajo para localizar y transformar los datos.  
  
 En el ejemplo de código siguiente se muestra el resultado de llamar al método **WriteXml** en el **conjunto de datos**.  
  
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
  
 Tenga en cuenta que la **clientes** elemento y el **pedidos** elementos se muestran como elementos del mismo nivel. Si deseara la **pedidos** elementos se muestren como elementos secundarios de sus respectivos elementos primarios, la **Nested** propiedad de la **DataRelation** tendría que estar establecido en **true** y debe agregar lo siguiente:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 El código siguiente muestra lo que el resultado sería, con el **pedidos** elementos anidados dentro de sus respectivos elementos primarios.  
  
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
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
