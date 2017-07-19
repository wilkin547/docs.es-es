---
title: "Escribir la informaci&#243;n de esquema de DataSet como XSD | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Escribir la informaci&#243;n de esquema de DataSet como XSD
Puede escribir el esquema de un <xref:System.Data.DataSet> como un esquema de lenguaje de definición de esquemas XML \(XSD\), de forma que pueda transportarlo, con o sin datos relacionados, a un documento XML.  El esquema XML, que se puede escribir en un archivo, una secuencia, un <xref:System.Xml.XmlWriter> o una cadena, es útil para generar un **DataSet** fuertemente tipado.  Para obtener más información sobre objetos **DataSet** fuertemente tipados, vea [DataSets con establecimiento de tipos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Puede especificar cómo se representa una columna de una tabla en el esquema XML mediante la propiedad **ColumnMapping** del objeto <xref:System.Data.DataColumn>.  Para obtener más información, vea "Asignar columnas a elementos, atributos y texto XML" en [Escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Para escribir el esquema de un **DataSet** como un esquema XML en un archivo, una secuencia o **XmlWriter**, utilice el método **WriteXmlSchema** del **DataSet**.  **WriteXmlSchema** toma un parámetro que especifica el destino del esquema XML resultante.  En los siguientes ejemplos de código se muestra cómo escribir el esquema XML de un **DataSet** en un archivo si se pasa una cadena que contiene un nombre de archivo y un objeto <xref:System.IO.StreamWriter>.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 Para obtener el esquema de un **DataSet** y escribirlo como una cadena de esquema XML, utilice el método **GetXmlSchema** como se muestra en el ejemplo siguiente.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## Vea también  
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [DataSets con establecimiento de tipos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)