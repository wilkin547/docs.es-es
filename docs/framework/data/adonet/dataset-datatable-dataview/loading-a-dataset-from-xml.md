---
title: Cargar un conjunto de datos desde XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: c21ed3bb31add285d64272040680433fff4e16fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151070"
---
# <a name="loading-a-dataset-from-xml"></a>Cargar un conjunto de datos desde XML
Es posible crear el contenido de un <xref:System.Data.DataSet> de ADO.NET a partir de una secuencia o de un documento XML. Además, con .NET Framework se dispone de una gran flexibilidad sobre qué información se carga desde XML y cómo se crea el esquema o la estructura relacional del <xref:System.Data.DataSet>.  
  
 Para rellenar <xref:System.Data.DataSet> un con datos de XML, <xref:System.Data.DataSet> utilice el **ReadXml** método del objeto. El **readXml** método lee de un archivo, una secuencia o un **XmlReader**, y toma como argumentos el origen del XML más un **xmlReadMode** opcional argumento. Para obtener más información acerca de **XmlReader**, vea Lectura de [datos XML con XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). El **ReadXml** método lee el contenido de la <xref:System.Data.DataSet> secuencia XML o documento y carga los datos con. También creará el esquema relacional <xref:System.Data.DataSet> de la en función de la **XmlReadMode** especificado y si ya existe o no un esquema relacional.  
  
 En la tabla siguiente se describen las opciones para el **XmlReadMode** argumento.  
  
|Opción|Descripción|  
|------------|-----------------|  
|**Automático**|Este es el valor predeterminado. Examina el código XML y elige la opción más apropiada, en el orden siguiente:<br /><br /> - Si el XML es un DiffGram, se utiliza **DiffGram.**<br />- Si <xref:System.Data.DataSet> contiene un esquema o el XML contiene un esquema en línea, se utiliza **ReadSchema.**<br />- Si <xref:System.Data.DataSet> el no contiene un esquema y el XML no contiene un esquema en línea, Se utiliza **InferSchema.**<br /><br /> Si conoce el formato del XML que se está leyendo, para obtener el mejor rendimiento se recomienda establecer un **XmlReadMode**explícito, en lugar de aceptar el valor predeterminado **Automático.**|  
|**ReadSchema**|Lee cualquier esquema alineado y carga los datos y el esquema.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se agregan nuevas tablas del esquema alineado al esquema existente en el <xref:System.Data.DataSet>. Si ya existe alguna tabla del esquema alineado en el <xref:System.Data.DataSet>, se iniciará una excepción. No podrá modificar el esquema de una tabla existente mediante **XmlReadMode.ReadSchema**.<br /><br /> Si el <xref:System.Data.DataSet> no contiene un esquema y no hay ningún esquema alineado, no se leerá ningún dato.<br /><br /> Es posible definir el esquema alineado mediante el esquema del lenguaje de definición de esquemas XML (XSD). Para obtener más información sobre cómo escribir el esquema en línea como esquema XML, vea Derivar la estructura relacional del conjunto de datos desde el [esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Pasa por alto cualquier esquema alineado y carga los datos en el esquema del <xref:System.Data.DataSet> existente. Se descartan todos los datos que no coincidan con el esquema existente. Si no existe ningún esquema en el <xref:System.Data.DataSet>, no se cargará ningún dato.<br /><br /> Si los datos son un DiffGram, **IgnoreSchema** tiene la misma funcionalidad que **DiffGram** *.*|  
|**InferSchema**|Pasa por alto cualquier esquema alineado, deduce el esquema por la estructura de los datos XML y, a continuación, carga los datos.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se extiende el esquema actual mediante la adición de columnas a las tablas existentes. Si no existen tablas, no se agregarán tablas adicionales. Se iniciará una excepción si ya existe una tabla inferida con un espacio de nombres diferente o si alguna columna inferida entra en conflicto con columnas existentes.<br /><br /> Para obtener más información sobre cómo **ReadXmlSchema** deduce un esquema de un documento XML, vea [Inferir](inferring-dataset-relational-structure-from-xml.md)estructura relacional de conjunto de datos de XML .|  
|**Diffgram**|Lee un DiffGram y agrega los datos al esquema actual. **DiffGram** combina nuevas filas con filas existentes donde los valores de identificador único coinciden. Vea "Combinar datos desde XML" al final de este tema. Para obtener más información acerca de DiffGrams, consulte [DiffGrams](diffgrams.md).|  
|**Fragmento**|Sigue leyendo varios fragmentos de XML hasta llegar al final de la secuencia. Los fragmentos que coinciden con el esquema del <xref:System.Data.DataSet> se anexan a las tablas apropiadas. Los fragmentos que no coinciden con el esquema del <xref:System.Data.DataSet> se descartan.|  
  
> [!NOTE]
> Si pasa un **XmlReader** a **ReadXml** que se coloca parte del camino en un documento XML, **ReadXml** leerá en el siguiente nodo de elemento y lo tratará como el elemento raíz, leyendo hasta el final del nodo de elemento solamente. Esto no se aplica si especifica **XmlReadMode.Fragment**.  
  
## <a name="dtd-entities"></a>Entidades DTD  
 Si el XML contiene entidades definidas en un esquema de definición de tipo de documento <xref:System.Data.DataSet> (DTD), se producirá una excepción si intenta cargar un nombre de archivo, una secuencia o un **XmlReader** no validado a **ReadXml**. En su lugar, debe crear un **XmlValidatingReader**, con **EntityHandling** establecido en **EntityHandling.ExpandEntities**, y pasar **el XmlValidatingReader** a **ReadXml**. **XmlValidatingReader** expandirá las entidades antes de <xref:System.Data.DataSet>ser leídos por el archivo .  
  
 En los siguientes ejemplos de código se muestra cómo cargar un <xref:System.Data.DataSet> desde una secuencia XML. En el primer ejemplo se muestra un nombre de archivo que se pasa a la **ReadXml** método. En el segundo ejemplo se muestra una cadena que contiene el código XML que se carga mediante un <xref:System.IO.StringReader>.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
> Si llama a **ReadXml** para cargar un archivo muy grande, es posible que encuentre un rendimiento lento. Para garantizar el mejor rendimiento para **ReadXml** <xref:System.Data.DataTable.BeginLoadData%2A> , en un <xref:System.Data.DataSet>archivo grande, llame al método para cada tabla de la , y, a continuación, llame a **ReadXml**. Por último, llame a <xref:System.Data.DataTable.EndLoadData%2A> para cada una de las tablas del <xref:System.Data.DataSet>, tal y como se muestra en el siguiente ejemplo.  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
> Si el esquema <xref:System.Data.DataSet> XSD para su incluye un **targetNamespace**, los datos pueden no ser <xref:System.Data.DataSet> leídos y puede encontrar excepciones, al llamar a **ReadXml** para cargar el XML con que contiene elementos sin espacio de nombres calificado. Para leer elementos no calificados en este caso, establezca **elementFormDefault** igual a "qualified" en el esquema XSD. Por ejemplo:  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a>Combinar datos a partir de XML  
 Si el <xref:System.Data.DataSet> ya contiene datos, los nuevos datos procedentes del código XML se agregarán a los ya presentes en el <xref:System.Data.DataSet>. **ReadXml** no se combina desde <xref:System.Data.DataSet> el XML en la información de fila con claves principales coincidentes. Para sobrescribir la información de fila existente con nueva <xref:System.Data.DataSet>información de <xref:System.Data.DataSet.Merge%2A> XML, use <xref:System.Data.DataSet> **ReadXml** para crear un nuevo y, a continuación, el nuevo <xref:System.Data.DataSet> en el archivo . Tenga en cuenta que cargar un DiffGram mediante **ReadXML** con un **XmlReadMode** de **DiffGram** combinará filas que tienen el mismo identificador único.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DiffGram](diffgrams.md)
- [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Carga de información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
