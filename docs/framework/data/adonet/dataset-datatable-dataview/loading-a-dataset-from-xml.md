---
title: Cargar un conjunto de datos desde XML
description: Obtenga información sobre cómo agregar contenido a un conjunto de ADO.NET de XML. El .NET Framework ofrece flexibilidad a la hora de cargar y la estructura del conjunto de elementos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 8c81e6e29678fe2e30af7c15d8d6e90f23dd0762
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286888"
---
# <a name="loading-a-dataset-from-xml"></a>Cargar un conjunto de datos desde XML
Es posible crear el contenido de un <xref:System.Data.DataSet> de ADO.NET a partir de una secuencia o de un documento XML. Además, con .NET Framework se dispone de una gran flexibilidad sobre qué información se carga desde XML y cómo se crea el esquema o la estructura relacional del <xref:System.Data.DataSet>.  
  
 Para rellenar <xref:System.Data.DataSet> con datos de XML, utilice el método **ReadXml** del <xref:System.Data.DataSet> objeto. El método **ReadXml** Lee de un archivo, una secuencia o un **XmlReader**y toma como argumentos el origen del XML más un argumento de **XmlReadMode** opcional. Para obtener más información acerca de **XmlReader**, vea [leer datos XML con XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). El método **ReadXml** lee el contenido de la secuencia o el documento XML y carga <xref:System.Data.DataSet> con los datos. También creará el esquema relacional de <xref:System.Data.DataSet> dependiendo del **XmlReadMode** especificado y de si ya existe o no un esquema relacional.  
  
 En la tabla siguiente se describen las opciones del argumento **XmlReadMode** .  
  
|Opción|Descripción|  
|------------|-----------------|  
|**Auto**|Este es el valor predeterminado. Examina el código XML y elige la opción más apropiada, en el orden siguiente:<br /><br /> -Si el XML es un DiffGram, se utiliza **DiffGram** .<br />-Si <xref:System.Data.DataSet> contiene un esquema o el XML contiene un esquema insertado, se utiliza **ReadSchema** .<br />-Si no <xref:System.Data.DataSet> contiene un esquema y el XML no contiene un esquema insertado, se utiliza **InferSchema** .<br /><br /> Si conoce el formato del XML que se está leyendo, para obtener el mejor rendimiento se recomienda establecer un **XmlReadMode**explícito, en lugar de aceptar el valor predeterminado **auto** .|  
|**ReadSchema**|Lee cualquier esquema alineado y carga los datos y el esquema.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se agregan nuevas tablas del esquema alineado al esquema existente en el <xref:System.Data.DataSet>. Si ya existe alguna tabla del esquema alineado en el <xref:System.Data.DataSet>, se iniciará una excepción. No podrá modificar el esquema de una tabla existente con **XmlReadMode. ReadSchema**.<br /><br /> Si el <xref:System.Data.DataSet> no contiene un esquema y no hay ningún esquema alineado, no se leerá ningún dato.<br /><br /> Es posible definir el esquema alineado mediante el esquema del lenguaje de definición de esquemas XML (XSD). Para obtener más información sobre cómo escribir esquemas insertados como esquemas XML, vea [derivar una estructura relacional de conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Pasa por alto cualquier esquema alineado y carga los datos en el esquema del <xref:System.Data.DataSet> existente. Se descartan todos los datos que no coincidan con el esquema existente. Si no existe ningún esquema en el <xref:System.Data.DataSet>, no se cargará ningún dato.<br /><br /> Si los datos son un DiffGram, **IgnoreSchema** tiene la misma funcionalidad que **DiffGram** *.*|  
|**InferSchema**|Pasa por alto cualquier esquema alineado, deduce el esquema por la estructura de los datos XML y, a continuación, carga los datos.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se extiende el esquema actual mediante la adición de columnas a las tablas existentes. Si no existen tablas, no se agregarán tablas adicionales. Se iniciará una excepción si ya existe una tabla inferida con un espacio de nombres diferente o si alguna columna inferida entra en conflicto con columnas existentes.<br /><br /> Para obtener más información sobre cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [inferir la estructura relacional de DataSet desde XML](inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Lee un DiffGram y agrega los datos al esquema actual. **DiffGram** combina las nuevas filas con las filas existentes donde coinciden los valores de identificador único. Vea "Combinar datos desde XML" al final de este tema. Para obtener más información acerca de los DiffGrams, vea [DiffGrams](diffgrams.md).|  
|**Fragment**|Sigue leyendo varios fragmentos de XML hasta llegar al final de la secuencia. Los fragmentos que coinciden con el esquema del <xref:System.Data.DataSet> se anexan a las tablas apropiadas. Los fragmentos que no coinciden con el esquema del <xref:System.Data.DataSet> se descartan.|  
  
> [!NOTE]
> Si pasa un **XmlReader** a un **ReadXml** que se coloca parte del camino en un documento XML, **ReadXml** leerá al siguiente nodo de elemento y lo tratará como el elemento raíz, leyendo hasta el final del nodo de elementos. Esto no se aplica si especifica **XmlReadMode. Fragment**.  
  
## <a name="dtd-entities"></a>Entidades DTD  
 Si el código XML contiene entidades definidas en un esquema de definición de tipo de documento (DTD), se iniciará una excepción si intenta cargar una <xref:System.Data.DataSet> pasando un nombre de archivo, una secuencia o un **XmlReader** de no validación a **ReadXml**. En su lugar, debe crear un **XmlValidatingReader**, con **EntityHandling** establecido en **EntityHandling. ExpandEntities**, y pasar el **XmlValidatingReader** a **ReadXml**. **XmlValidatingReader** expandirá las entidades antes de que las lea <xref:System.Data.DataSet> .  
  
 En los siguientes ejemplos de código se muestra cómo cargar un <xref:System.Data.DataSet> desde una secuencia XML. En el primer ejemplo se muestra un nombre de archivo que se pasa al método **ReadXml** . En el segundo ejemplo se muestra una cadena que contiene el código XML que se carga mediante un <xref:System.IO.StringReader>.  
  
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
> Si llama a **ReadXml** para cargar un archivo muy grande, puede experimentar un rendimiento lento. Para garantizar el mejor rendimiento de **ReadXml**, en un archivo de gran tamaño, llame al <xref:System.Data.DataTable.BeginLoadData%2A> método para cada tabla de <xref:System.Data.DataSet> y, a continuación, llame a **ReadXml**. Por último, llame a <xref:System.Data.DataTable.EndLoadData%2A> para cada una de las tablas del <xref:System.Data.DataSet>, tal y como se muestra en el siguiente ejemplo.  
  
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
> Si el esquema XSD para <xref:System.Data.DataSet> incluye un elemento **targetNamespace**, es posible que no se lean los datos y que se produzcan excepciones al llamar a **ReadXml** para cargar el <xref:System.Data.DataSet> elemento con XML que contiene elementos sin espacio de nombres calificado. Para leer elementos incompletos en este caso, establezca **elementFormDefault** en "Qualified" en el esquema XSD. Por ejemplo:  
  
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
 Si el <xref:System.Data.DataSet> ya contiene datos, los nuevos datos procedentes del código XML se agregarán a los ya presentes en el <xref:System.Data.DataSet>. **ReadXml** no combina el XML con la información de <xref:System.Data.DataSet> ninguna fila con claves principales coincidentes. Para sobrescribir la información de fila existente con la nueva información de XML, utilice **ReadXml** para crear una nueva <xref:System.Data.DataSet> y, a continuación, <xref:System.Data.DataSet.Merge%2A> la nueva <xref:System.Data.DataSet> en la existente <xref:System.Data.DataSet> . Tenga en cuenta que al cargar un DiffGram mediante **ReadXml** con un **XmlReadMode** de **DiffGram** , se combinarán las filas que tengan el mismo identificador único.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DiffGram](diffgrams.md)
- [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
