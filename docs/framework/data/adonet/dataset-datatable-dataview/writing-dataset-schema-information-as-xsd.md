---
title: Escribir información del esquema de un conjunto de datos como XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 7634dfc8415b6f73fc60f2ebe59c92a0c31f83a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173736"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Escribir información del esquema de un conjunto de datos como XSD

Puede escribir el esquema de un <xref:System.Data.DataSet> como un esquema de lenguaje de definición de esquemas XML (XSD), de forma que pueda transportarlo, con o sin datos relacionados, a un documento XML. El esquema XML se puede escribir en un archivo, una secuencia, un <xref:System.Xml.XmlWriter> o una cadena; resulta útil para generar un **conjunto**de un DataSet fuertemente tipado. Para obtener más información sobre los objetos de **conjunto** de datos fuertemente tipados, vea [conjuntos de datos con tipo](typed-datasets.md).  
  
 Puede especificar cómo se representa una columna de una tabla en el esquema XML mediante la propiedad **ColumnMapping** del <xref:System.Data.DataColumn> objeto. Para obtener más información, vea "asignar columnas a elementos, atributos y texto XML" al [escribir el contenido del conjunto de datos como datos XML](writing-dataset-contents-as-xml-data.md).  
  
 Para escribir el esquema de un **DataSet** como esquema XML, en un archivo, una secuencia o **XmlWriter**, utilice el método **WriteXmlSchema** del **conjunto**de archivos. **WriteXmlSchema** toma un parámetro que especifica el destino del esquema XML resultante. En los siguientes ejemplos de código se muestra cómo escribir el esquema XML de un **conjunto** de objetos en un archivo pasando una cadena que contiene un nombre de archivo y un <xref:System.IO.StreamWriter> objeto.  
  
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
  
 Para obtener el esquema de un **DataSet** y escribirlo como una cadena de esquema XML, use el método **GetXmlSchema** , como se muestra en el ejemplo siguiente.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Vea también

- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Escribir el contenido de un conjunto de datos como datos XML](writing-dataset-contents-as-xml-data.md)
- [Objetos DataSet con tipo](typed-datasets.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
