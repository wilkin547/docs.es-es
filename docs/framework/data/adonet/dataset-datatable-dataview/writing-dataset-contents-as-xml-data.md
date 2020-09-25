---
title: Escribir el contenido de un conjunto de datos como datos XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: c8a5c747e4ec60fcb97edf631aa3a0ae184ffec5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173723"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Escribir el contenido de un conjunto de datos como datos XML

En ADO.NET es posible escribir una representación XML de un <xref:System.Data.DataSet>, con o sin su esquema. Si la información de esquema está incluida alineada con el código XML, se escribirá con el lenguaje de definición de esquemas XML (XSD). El esquema contiene las definiciones de tabla del <xref:System.Data.DataSet>, así como las definiciones de relaciones y restricciones.  
  
 Cuando un <xref:System.Data.DataSet> se escribe como datos XML, las filas del <xref:System.Data.DataSet> se escriben en sus versiones actuales. Sin embargo, el <xref:System.Data.DataSet> también se puede escribir como un DiffGram, de forma que se incluyan los valores actuales y originales de las filas.  
  
 La representación XML de <xref:System.Data.DataSet> se puede escribir en un archivo, una secuencia, un **XmlWriter**o una cadena. Estas opciones ofrecen una gran flexibilidad en cuanto a la forma de transportar la representación XML del <xref:System.Data.DataSet>. Para obtener la representación XML de <xref:System.Data.DataSet> como una cadena, utilice el método **GetXml** tal y como se muestra en el ejemplo siguiente.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** devuelve la representación XML de <xref:System.Data.DataSet> sin información del esquema. Para escribir la información de esquema del <xref:System.Data.DataSet> (como esquema XML) en una cadena, utilice **GetXmlSchema**.  
  
 Para escribir un <xref:System.Data.DataSet> en un archivo, una secuencia o **XmlWriter**, utilice el método **WriteXml** . El primer parámetro que se pasa a **WriteXml** es el destino de la salida XML. Por ejemplo, pase una cadena que contenga un nombre de archivo, un objeto **System. IO. TextWriter** , etc. Puede pasar un segundo parámetro opcional de un **XmlWriteMode** para especificar cómo se escribirá la salida XML.  
  
 En la tabla siguiente se muestran las opciones de **XmlWriteMode**.  
  
|Opción XmlWriteMode|Descripción|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Escribe el contenido actual del <xref:System.Data.DataSet> como datos XML, sin un esquema XML. Este es el valor predeterminado.|  
|**WriteSchema**|Escribe el contenido actual del <xref:System.Data.DataSet> como datos XML con la estructura relacional como un esquema XML alineado.|  
|**DiffGram**|Escribe el <xref:System.Data.DataSet> completo como un DiffGram, incluidos los valores originales y actuales. Para obtener más información, vea [DiffGrams](diffgrams.md).|  
  
 Al escribir una representación XML de un <xref:System.Data.DataSet> objeto que contiene objetos **DataRelation** , lo más probable es que desee que el XML resultante tenga las filas secundarias de cada relación anidadas dentro de sus elementos primarios relacionados. Para ello, establezca la propiedad **Nested** de la **DataRelation** en **true** cuando agregue la **DataRelation** a <xref:System.Data.DataSet> . Para obtener más información, consulte anidamiento de objetos [DataRelation](nesting-datarelations.md).  
  
 A continuación se muestran dos ejemplos de cómo escribir la representación XML de un <xref:System.Data.DataSet> en un archivo. En el primer ejemplo se pasa el nombre de archivo para el XML resultante como una cadena a **WriteXml**. En el segundo ejemplo se pasa un objeto **System. IO. StreamWriter** .
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a>Asignar columnas a elementos, atributos y texto XML  

 Puede especificar cómo se representa una columna de una tabla en XML mediante la propiedad **ColumnMapping** del objeto **DataColumn** . En la tabla siguiente se muestran los diferentes valores de **MappingType** para la propiedad **ColumnMapping** de una columna de tabla y el XML resultante.  
  
|Valor MappingType|Descripción|  
|-----------------------|-----------------|  
|**Element**|Este es el valor predeterminado. La columna se escribe como un elemento XML, donde ColumnName es el nombre del elemento y el contenido de la columna se escribe como el texto del elemento. Por ejemplo:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Atributo**|La columna se escribe como un atributo XML del elemento XML para la fila actual, donde ColumnName es el nombre del atributo y el contenido de la columna se escribe como el valor del atributo. Por ejemplo:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|El contenido de la columna se escribe como texto en el elemento XML de la fila actual. Por ejemplo:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Tenga en cuenta que **SimpleContent** no se puede establecer para una columna de una tabla que tenga columnas de **elementos** o relaciones anidadas.|  
|**Oculto**|La columna no se escribe en el resultado XML.|  
  
## <a name="see-also"></a>Vea también

- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DiffGram](diffgrams.md)
- [Anidar objetos DataRelation](nesting-datarelations.md)
- [Escribir información del esquema de un conjunto de datos como XSD](writing-dataset-schema-information-as-xsd.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
