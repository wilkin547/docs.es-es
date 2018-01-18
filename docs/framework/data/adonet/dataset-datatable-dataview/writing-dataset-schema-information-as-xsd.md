---
title: "Escribir información del esquema de un conjunto de datos como XSD"
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
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bea961310c838068a54f15f7b05186ab56721dc2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Escribir información del esquema de un conjunto de datos como XSD
Puede escribir el esquema de un <xref:System.Data.DataSet> como un esquema de lenguaje de definición de esquemas XML (XSD), de forma que pueda transportarlo, con o sin datos relacionados, a un documento XML. Esquema XML se puede escribir en un archivo, una secuencia, un <xref:System.Xml.XmlWriter>, o una cadena; resulta útil para generar un fuertemente tipado **conjunto de datos**. Para obtener más información acerca de establecimiento inflexible de tipos **conjunto de datos** los objetos, vea [conjuntos de datos con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Puede especificar cómo se representa una columna de una tabla en el esquema XML utilizando la **ColumnMapping** propiedad de la <xref:System.Data.DataColumn> objeto. Para obtener más información, vea "Asignar columnas a elementos, atributos y texto XML" en [escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Para escribir el esquema de un **conjunto de datos** como un esquema XML a un archivo, secuencia, o **XmlWriter**, use la **WriteXmlSchema** método de la **conjunto de datos**. **WriteXmlSchema** toma un parámetro que especifica el destino del esquema XML resultante. Los ejemplos de código siguientes muestran cómo escribir el esquema XML de un **conjunto de datos** a un archivo si se pasa una cadena que contiene un nombre de archivo y un <xref:System.IO.StreamWriter> objeto.  
  
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
  
 Para obtener el esquema de un **conjunto de datos** y escribirlo como una cadena de esquema XML, utilice el **GetXmlSchema** método, tal como se muestra en el ejemplo siguiente.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Escritura de contenido de un conjunto de datos como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [Objetos DataSet con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
