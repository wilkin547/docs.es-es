---
title: Escribir el contenido de un conjunto de datos como datos XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: ff63c63be9bbfab7c3a9600f259abdea81be4260
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43724479"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Escribir el contenido de un conjunto de datos como datos XML
En ADO.NET es posible escribir una representación XML de un <xref:System.Data.DataSet>, con o sin su esquema. Si la información de esquema está incluida alineada con el código XML, se escribirá con el lenguaje de definición de esquemas XML (XSD). El esquema contiene las definiciones de tabla del <xref:System.Data.DataSet>, así como las definiciones de relaciones y restricciones.  
  
 Cuando un <xref:System.Data.DataSet> se escribe como datos XML, las filas del <xref:System.Data.DataSet> se escriben en sus versiones actuales. Sin embargo, el <xref:System.Data.DataSet> también se puede escribir como un DiffGram, de forma que se incluyan los valores actuales y originales de las filas.  
  
 La representación XML de la <xref:System.Data.DataSet> pueden escribirse en un archivo, una secuencia, un **XmlWriter**, o una cadena. Estas opciones ofrecen una gran flexibilidad en cuanto a la forma de transportar la representación XML del <xref:System.Data.DataSet>. Para obtener la representación XML de la <xref:System.Data.DataSet> como una cadena, utilice el **GetXml** método tal como se muestra en el ejemplo siguiente.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** devuelve la representación XML de la <xref:System.Data.DataSet> sin información del esquema. Para escribir la información de esquema desde el <xref:System.Data.DataSet> (como esquema XML) en una cadena, utilice **GetXmlSchema**.  
  
 Para escribir un <xref:System.Data.DataSet> en un archivo, secuencia, o **XmlWriter**, utilice el **WriteXml** método. El primer parámetro se pasa a **WriteXml** constituye el destino de la salida XML. Por ejemplo, pasar una cadena que contiene un nombre de archivo, un **System.IO.TextWriter** objeto y así sucesivamente. Puede pasar un segundo parámetro opcional de un **XmlWriteMode** para especificar cómo se escribirá la salida XML.  
  
 En la tabla siguiente se muestra las opciones para **XmlWriteMode**.  
  
|Opción XmlWriteMode|Descripción|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Escribe el contenido actual del <xref:System.Data.DataSet> como datos XML, sin un esquema XML. Este es el valor predeterminado.|  
|**WriteSchema**|Escribe el contenido actual del <xref:System.Data.DataSet> como datos XML con la estructura relacional como un esquema XML alineado.|  
|**DiffGram**|Escribe el <xref:System.Data.DataSet> completo como un DiffGram, incluidos los valores originales y actuales. Para obtener más información, consulte [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
  
 Al escribir una representación XML de un <xref:System.Data.DataSet> que contiene **DataRelation** objetos, probablemente le interesará el código XML resultante tenga las filas secundarias de cada relación anidadas dentro de sus elementos primarios relacionados. Para ello, establezca el **Nested** propiedad de la **DataRelation** a **true** al agregar el **DataRelation** a la <xref:System.Data.DataSet>. Para obtener más información, consulte [anidar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
 A continuación se muestran dos ejemplos de cómo escribir la representación XML de un <xref:System.Data.DataSet> en un archivo. El primer ejemplo pasa el nombre de archivo para el XML resultante como una cadena a **WriteXml**. El segundo ejemplo se pasa un **System.IO.StreamWriter** objeto.  
  
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
 Puede especificar cómo se representa una columna de una tabla en XML mediante el **ColumnMapping** propiedad de la **DataColumn** objeto. En la tabla siguiente se muestra los distintos **MappingType** valores para el **ColumnMapping** propiedad de una columna de tabla y el XML resultante.  
  
|Valor MappingType|Descripción|  
|-----------------------|-----------------|  
|**Element**|Este es el valor predeterminado. La columna se escribe como un elemento XML, donde ColumnName es el nombre del elemento y el contenido de la columna se escribe como el texto del elemento. Por ejemplo:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Attribute**|La columna se escribe como un atributo XML del elemento XML para la fila actual, donde ColumnName es el nombre del atributo y el contenido de la columna se escribe como el valor del atributo. Por ejemplo:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|El contenido de la columna se escribe como texto en el elemento XML de la fila actual. Por ejemplo:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Tenga en cuenta que **SimpleContent** no se puede establecer para una columna de una tabla que tiene **elemento** columnas o relaciones anidadas.|  
|**Oculto**|La columna no se escribe en el resultado XML.|  
  
## <a name="see-also"></a>Vea también  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [Anidado de objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [Escritura de información del esquema de un conjunto de datos como XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
