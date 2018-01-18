---
title: Cargar un conjunto de datos desde XML
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
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1d0c98224b8b508fec5fe584388872757a9dfdf3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="loading-a-dataset-from-xml"></a>Cargar un conjunto de datos desde XML
Es posible crear el contenido de un <xref:System.Data.DataSet> de ADO.NET a partir de una secuencia o de un documento XML. Además, con .NET Framework se dispone de una gran flexibilidad sobre qué información se carga desde XML y cómo se crea el esquema o la estructura relacional del <xref:System.Data.DataSet>.  
  
 Para rellenar un <xref:System.Data.DataSet> con datos de XML, utilice el **ReadXml** método de la <xref:System.Data.DataSet> objeto. El **ReadXml** método lee de un archivo, una secuencia, o un **XmlReader**y toma como argumentos el origen de XML y un elemento opcional **XmlReadMode** argumento. (Para obtener más información sobre la **XmlReader**, consulte [NIB: leer datos de XML con XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) El **ReadXml** método lee el contenido de la secuencia XML o documentos y carga el <xref:System.Data.DataSet> con datos. También creará el esquema relacional de la <xref:System.Data.DataSet> en función de la **XmlReadMode** especificado y si ya existe un esquema relacional.  
  
 En la tabla siguiente se describe las opciones para la **XmlReadMode** argumento.  
  
|Opción|Descripción|  
|------------|-----------------|  
|**Auto**|Este es el valor predeterminado. Examina el código XML y elige la opción más apropiada, en el orden siguiente:<br /><br /> -Si el XML es un DiffGram, **DiffGram** se utiliza.<br />-If el <xref:System.Data.DataSet> contiene un esquema o el código XML contiene un esquema insertado, **ReadSchema** se utiliza.<br />-If el <xref:System.Data.DataSet> no contiene un esquema y el código XML no contiene un esquema insertado, **InferSchema** se utiliza.<br /><br /> Si conoce el formato del XML que se está leyendo, para mejorar el rendimiento se recomienda establecer explícito **XmlReadMode**, en lugar de permitir el **automática** predeterminado.|  
|**ReadSchema**|Lee cualquier esquema alineado y carga los datos y el esquema.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se agregan nuevas tablas del esquema alineado al esquema existente en el <xref:System.Data.DataSet>. Si ya existe alguna tabla del esquema alineado en el <xref:System.Data.DataSet>, se iniciará una excepción. No podrá modificar el esquema de una tabla existente mediante **XmlReadMode.ReadSchema**.<br /><br /> Si el <xref:System.Data.DataSet> no contiene un esquema y no hay ningún esquema alineado, no se leerá ningún dato.<br /><br /> Es posible definir el esquema alineado mediante el esquema del lenguaje de definición de esquemas XML (XSD). Para obtener más información acerca de cómo escribir el esquema en línea como esquema XML, vea [derivar estructura relacional de DataSet de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Pasa por alto cualquier esquema alineado y carga los datos en el esquema del <xref:System.Data.DataSet> existente. Se descartan todos los datos que no coincidan con el esquema existente. Si no existe ningún esquema en el <xref:System.Data.DataSet>, no se cargará ningún dato.<br /><br /> Si los datos son un DiffGram, **IgnoreSchema** tiene la misma funcionalidad que **DiffGram** *.*|  
|**InferSchema**|Pasa por alto cualquier esquema alineado, deduce el esquema por la estructura de los datos XML y, a continuación, carga los datos.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se extiende el esquema actual mediante la adición de columnas a las tablas existentes. Si no existen tablas, no se agregarán tablas adicionales. Se iniciará una excepción si ya existe una tabla inferida con un espacio de nombres diferente o si alguna columna inferida entra en conflicto con columnas existentes.<br /><br /> Para obtener más información acerca de cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [deducir el conjunto de datos relacional estructura de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Lee un DiffGram y agrega los datos al esquema actual. **DiffGram** combina las filas nuevas con las filas existentes que coincidan con los valores de identificador único. Vea "Combinar datos desde XML" al final de este tema. Para obtener más información acerca de los DiffGrams, vea [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Fragment**|Sigue leyendo varios fragmentos de XML hasta llegar al final de la secuencia. Los fragmentos que coinciden con el esquema del <xref:System.Data.DataSet> se anexan a las tablas apropiadas. Los fragmentos que no coinciden con el esquema del <xref:System.Data.DataSet> se descartan.|  
  
> [!NOTE]
>  Si se pasa un **XmlReader** a **ReadXml** decir posicionada parte de la forma en un documento XML, **ReadXml** leerá hasta el siguiente nodo de elemento y lo considerará la raíz elemento, leyendo hasta el final del nodo de elemento únicamente. Esto no se aplica si especifica **XmlReadMode.Fragment**.  
  
## <a name="dtd-entities"></a>Entidades DTD  
 Si el código XML contiene entidades definidas en un esquema de definición (DTD) de tipo de documento, se producirá una excepción si intenta cargar un <xref:System.Data.DataSet> pasando un archivo de nombre, una secuencia o no validación **XmlReader** a  **ReadXml**. En su lugar, debe crear un **XmlValidatingReader**, con **EntityHandling** establecido en **EntityHandling.ExpandEntities**y pase el  **XmlValidatingReader** a **ReadXml**. El **XmlValidatingReader** expandirá las entidades antes de que se lea el <xref:System.Data.DataSet>.  
  
 En los siguientes ejemplos de código se muestra cómo cargar un <xref:System.Data.DataSet> desde una secuencia XML. El primer ejemplo muestra un nombre de archivo que se pasan a la **ReadXml** método. En el segundo ejemplo se muestra una cadena que contiene el código XML que se carga mediante un <xref:System.IO.StringReader>.  
  
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
>  Si se llama a **ReadXml** para cargar un archivo muy grande, puede encontrar un rendimiento lento. Para garantizar un rendimiento óptimo con **ReadXml**, en un archivo grande, llame a la <xref:System.Data.DataTable.BeginLoadData%2A> método para cada tabla en la <xref:System.Data.DataSet>y, a continuación, llame a **ReadXml**. Por último, llame a <xref:System.Data.DataTable.EndLoadData%2A> para cada una de las tablas del <xref:System.Data.DataSet>, tal y como se muestra en el siguiente ejemplo.  
  
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
>  Si el esquema XSD para su <xref:System.Data.DataSet> incluye un **targetNamespace**, no se pueden leer los datos y pueden aparecer excepciones al llamar a **ReadXml** para cargar el <xref:System.Data.DataSet> con XML que contenga elementos con un espacio de nombres sin calificación. Para leer elementos no calificados en este caso, establezca **elementFormDefault** igual a "qualified" en el esquema XSD. Por ejemplo:  
  
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
 Si el <xref:System.Data.DataSet> ya contiene datos, los nuevos datos procedentes del código XML se agregarán a los ya presentes en el <xref:System.Data.DataSet>. **ReadXml** no combina a partir de XML en el <xref:System.Data.DataSet> ninguna información con claves principales coincidentes de fila. Para sobrescribir información de fila existente con nueva información procedente de XML, utilice **ReadXml** para crear un nuevo <xref:System.Data.DataSet>y, a continuación, <xref:System.Data.DataSet.Merge%2A> nuevo <xref:System.Data.DataSet> existentes <xref:System.Data.DataSet>. Tenga en cuenta que al cargar un DiffGram mediante **ReadXML** con una **XmlReadMode** de **DiffGram** se combinarán las filas que tienen el mismo identificador único.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Inferencia de una estructura relacional de un conjunto de datos a partir de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Carga de información del esquema de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
