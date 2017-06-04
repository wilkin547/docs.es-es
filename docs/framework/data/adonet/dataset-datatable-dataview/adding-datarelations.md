---
title: "Agregar DataRelations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Agregar DataRelations
En un <xref:System.Data.DataSet> que contiene varios objetos <xref:System.Data.DataTable>, es posible utilizar objetos <xref:System.Data.DataRelation> para relacionar una tabla con otra, navegar por las tablas y devolver filas secundarias o primarias de una tabla relacionada.  
  
 Los argumentos necesarios para crear una **DataRelation** son un nombre para la **DataRelation** que se va a crear y una matriz de una o más referencias <xref:System.Data.DataColumn> a las columnas que actúan como columnas primaria y secundaria en la relación.  Una vez creado un objeto **DataRelation**, es posible utilizarlo para navegar por las tablas y recuperar valores.  
  
 Al agregar una **DataRelation** a una <xref:System.Data.DataSet>, se agrega de forma predeterminada una <xref:System.Data.UniqueConstraint> a la tabla primaria y una <xref:System.Data.ForeignKeyConstraint> a la tabla secundaria.  Para obtener más información sobre cómo crear restricciones, vea [Restricciones de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 En el siguiente ejemplo de código se crea una **DataRelation** mediante dos objetos <xref:System.Data.DataTable> en un <xref:System.Data.DataSet>.  Cada <xref:System.Data.DataTable> contiene una columna denominada **CustID**, que actúa como vínculo entre los dos objetos <xref:System.Data.DataTable>.  En el ejemplo se agrega una única **DataRelation** a la colección **Relations** del <xref:System.Data.DataSet>.  El primer argumento del ejemplo especifica el nombre de la **DataRelation** que se va a crear.  El segundo argumento establece la **DataColumn** primaria y el tercer argumento establece la **DataColumn** secundaria.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 Una **DataRelation** tiene también una propiedad **Nested** que, cuando tiene el valor **true**, hace que las filas de la tabla secundaria se aniden dentro de la fila asociada de la tabla primaria cuando se escriben como elementos XML mediante <xref:System.Data.DataSet.WriteXml%2A>.  Para obtener más información, consulta [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## Vea también  
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)