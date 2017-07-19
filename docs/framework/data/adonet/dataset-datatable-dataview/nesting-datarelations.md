---
title: "Anidar DataRelations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Anidar DataRelations
En una representación relacional de datos, las tablas individuales contienen filas que están relacionadas entre sí por una columna o un conjunto de columnas.  En el <xref:System.Data.DataSet> de ADO.NET, la relación entre tablas se implementa mediante una <xref:System.Data.DataRelation>.  Cuando crea una **DataRelation**, las relaciones primaria\-secundaria de las columnas se administran sólo mediante la relación.  Las tablas y las columnas son entidades independientes.  En la representación jerárquica de los datos proporcionada por XML, las relaciones primaria\-secundaria se representan mediante elementos primarios que contienen elementos secundarios anidados.  
  
 Para facilitar el anidamiento de objetos secundarios cuando un **DataSet** se sincroniza con un <xref:System.Xml.XmlDataDocument> o se escribe como XML mediante **WriteXml**, la **DataRelation** expone una propiedad **Nested**.  Al establecer la propiedad **Nested** de una **DataRelation** como **true**, las filas secundarias de la relación se anidan dentro de la columna primaria cuando se escriben como datos XML o cuando se sincronizan con un **XmlDataDocument**.  La propiedad **Nested** de la **DataRelation** es **false** de manera predeterminada.  
  
 Por ejemplo, considere el siguiente **DataSet**.  
  
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
  
 Como la propiedad **Nested** del objeto **DataRelation** no tiene el valor **true** para este **DataSet**, los objetos secundarios no se anidarán dentro de los elementos primarios cuando este **DataSet** se represente como datos XML.  La transformación de la representación XML de un objeto **DataSet** que contiene objetos **DataSet** relacionados con relaciones de datos no anidadas puede provocar un rendimiento lento.  Se recomienda anidar las relaciones de datos.  Para ello, debe establecer la propiedad **Nested** en **True**.  A continuación, debe escribir código en la hoja de estilos XSLT que utilice expresiones de consulta XPath con jerarquía de arriba a abajo para localizar y transformar los datos.  
  
 En el siguiente ejemplo de código se muestra el resultado de llamar a **WriteXml** en el **DataSet**.  
  
```  
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
  
 Hay que tener en cuenta que el elemento **Customers** y los elementos **Orders** se muestran como elementos relacionados.  Si desea que los elementos **Orders** aparezcan como secundarios de sus respectivos elementos primarios, la propiedad **Nested** de la **DataRelation** debe ser **true** y se debe agregar lo siguiente:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 En el siguiente código se muestra cuál sería el resultado, con los elementos **Orders** anidados dentro de sus respectivos elementos primarios.  
  
```  
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
  
## Vea también  
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Agregar DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)