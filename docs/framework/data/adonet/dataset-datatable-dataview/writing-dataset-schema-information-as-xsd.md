---
title: Escribir información del esquema de un conjunto de datos como XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 2a59a9fc1c3b2f52543f4cc69de22a5703fa9b8b
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862780"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Escribir información del esquema de un conjunto de datos como XSD
Puede escribir el esquema de un <xref:System.Data.DataSet> como un esquema de lenguaje de definición de esquemas XML (XSD), de forma que pueda transportarlo, con o sin datos relacionados, a un documento XML. Esquema XML se puede escribir en un archivo, una secuencia, un <xref:System.Xml.XmlWriter>, o una cadena; es útil para generar un fuertemente tipado **DataSet**. Para obtener más información acerca de establecimiento inflexible de tipos **DataSet** objetos, vea [DataSets con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Puede especificar cómo se representa una columna de una tabla de esquema XML utilizando el **ColumnMapping** propiedad de la <xref:System.Data.DataColumn> objeto. Para obtener más información, vea "Asignar columnas a elementos, atributos y texto XML" en [escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Para escribir el esquema de un **conjunto de datos** como un esquema XML a un archivo, secuencia, o **XmlWriter**, utilice el **WriteXmlSchema** método de la **conjunto de datos**. **WriteXmlSchema** toma un parámetro que especifica el destino del esquema XML resultante. Los ejemplos de código siguientes muestran cómo escribir el esquema XML de un **DataSet** a un archivo pasando una cadena que contiene un nombre de archivo y un <xref:System.IO.StreamWriter> objeto.  
  
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
  
 Para obtener el esquema de un **DataSet** y escribirlo como una cadena de esquema XML, utilice el **GetXmlSchema** método, como se muestra en el ejemplo siguiente.  
  
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
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
