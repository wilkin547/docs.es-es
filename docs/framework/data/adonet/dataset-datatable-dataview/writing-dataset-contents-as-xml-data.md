---
title: "Escribir el contenido de un conjunto de datos como datos XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Escribir el contenido de un conjunto de datos como datos XML
En ADO.NET puede escribir una representación XML de un <xref:System.Data.DataSet>, con o sin su esquema. Si la información de esquema está incluida alineada con el código XML, se escribirá con el lenguaje de definición de esquemas XML (XSD). El esquema contiene las definiciones de tabla de la <xref:System.Data.DataSet> , así como las definiciones de relaciones y restricciones.  
  
 Cuando un <xref:System.Data.DataSet> se escribe como datos XML, las filas de la <xref:System.Data.DataSet> se escriben en sus versiones actuales. Sin embargo, el <xref:System.Data.DataSet> también se puede escribir como un DiffGram para que se incluyan actual y los valores originales de las filas.  
  
 La representación XML de la <xref:System.Data.DataSet> pueden escribirse en un archivo, una secuencia, un **XmlWriter**, o una cadena. Estas opciones ofrecen una gran flexibilidad para la forma de transportar la representación XML de la <xref:System.Data.DataSet>. Para obtener la representación XML de la <xref:System.Data.DataSet> como una cadena, utilice la **GetXml** método tal como se muestra en el ejemplo siguiente.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** devuelve la representación XML de la <xref:System.Data.DataSet> sin información del esquema. Para escribir la información de esquema de la <xref:System.Data.DataSet> (como esquema XML) en una cadena, utilice **GetXmlSchema**.  
  
 Para escribir una <xref:System.Data.DataSet> en un archivo, secuencia, o **XmlWriter**, utilice el **WriteXml** (método). El primer parámetro se pasa a **WriteXml** es el destino del resultado XML. Por ejemplo, pasar una cadena que contiene un nombre de archivo, un **System.IO.TextWriter** objeto y así sucesivamente. Puede pasar un segundo parámetro opcional de un **XmlWriteMode** para especificar cómo se escribirá el resultado XML.  
  
 La siguiente tabla muestra las opciones de **XmlWriteMode**.  
  
|Opción XmlWriteMode|Descripción|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Escribe el contenido actual de la <xref:System.Data.DataSet> como datos XML, sin un esquema XML. Este es el valor predeterminado.|  
|**WriteSchema**|Escribe el contenido actual de la <xref:System.Data.DataSet> como datos XML con la estructura relacional como un esquema XML en línea.|  
|**DiffGram**|Escribe todo el <xref:System.Data.DataSet> como un DiffGram, incluidos los valores originales y actuales. Para obtener más información, consulte [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
  
 Al escribir una representación XML de un <xref:System.Data.DataSet> que contiene **DataRelation** objetos, probablemente desearán el código XML resultante tenga las filas secundarias de cada relación anidadas dentro de sus elementos primarios relacionados. Para ello, establezca la **Nested** propiedad de la **DataRelation** a **true** al agregar el **DataRelation** a la <xref:System.Data.DataSet>. Para obtener más información, consulte [Anidar DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
 A continuación se muestran dos ejemplos de cómo escribir la representación XML de un <xref:System.Data.DataSet> a un archivo. El primer ejemplo pasa el nombre de archivo para el XML resultante como una cadena a **WriteXml**. El segundo ejemplo se pasa un **System.IO.StreamWriter** objeto.  
  
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
 Puede especificar cómo se representa una columna de una tabla en XML mediante el **ColumnMapping** propiedad de la **DataColumn** objeto. En la tabla siguiente se muestra los distintos **MappingType** los valores para la **ColumnMapping** propiedad de una columna de tabla y el XML resultante.  
  
|Valor MappingType|Descripción|  
|-----------------------|-----------------|  
|**Elemento**|Este es el valor predeterminado. La columna se escribe como un elemento XML, donde ColumnName es el nombre del elemento y el contenido de la columna se escribe como el texto del elemento. Por ejemplo:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Atributo**|La columna se escribe como un atributo XML del elemento XML para la fila actual, donde ColumnName es el nombre del atributo y el contenido de la columna se escribe como el valor del atributo. Por ejemplo:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|El contenido de la columna se escribe como texto en el elemento XML de la fila actual. Por ejemplo:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Tenga en cuenta que **SimpleContent** no se puede establecer para una columna de una tabla que tiene **elemento** columnas o relaciones anidadas.|  
|**Oculto**|La columna no se escribe en el resultado XML.|  
  
## <a name="see-also"></a>Vea también  
 [Uso de XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)   
 [Anidar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)   
 [Escribir información de esquema de DataSet como XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)   
 [DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Centro de desarrolladores de conjunto de datos y proveedores administrados de ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)