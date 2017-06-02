---
title: "Cargar DataSet desde XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Cargar DataSet desde XML
Es posible crear el contenido de un <xref:System.Data.DataSet> de ADO.NET a partir de una secuencia o de un documento XML.  Además, con .NET Framework se dispone de una gran flexibilidad sobre qué información se carga desde XML y cómo se crea el esquema o la estructura relacional del <xref:System.Data.DataSet>.  
  
 Para rellenar un <xref:System.Data.DataSet> con datos XML, utilice el método **ReadXml** del objeto <xref:System.Data.DataSet>.  El método **ReadXml** lee desde un archivo, una secuencia o un **XmlReader** y toma como argumentos el origen de XML y un argumento **XmlReadMode** opcional.  Para obtener más información sobre el **XmlReader**, vea [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/es-es/762c069b-b50c-41b8-936e-39eacfb0d540). El método **ReadXml** lee el contenido de la secuencia o el documento XML y carga datos en el <xref:System.Data.DataSet>.  También crea el esquema relacional del <xref:System.Data.DataSet> dependiendo del **XmlReadMode** especificado y de si ya existe o no un esquema relacional.  
  
 En la tabla siguiente se describen las opciones para el argumento **XmlReadMode**.  
  
|Opción|Descripción|  
|------------|-----------------|  
|**Auto**|Este es el valor predeterminado.  Examina el código XML y elige la opción más apropiada, en el orden siguiente:<br /><br /> -   Si el código XML es un DiffGram, se utiliza **DiffGram**.<br />-   Si el <xref:System.Data.DataSet> contiene un esquema o el código XML contiene un esquema alineado, se utiliza **ReadSchema**.<br />-   Si el <xref:System.Data.DataSet> no contiene un esquema y el código XML no contiene un esquema alineado, se utiliza **InferSchema**.<br /><br /> Si conoce el formato del código XML que se está leyendo, para mejorar el rendimiento se recomienda establecer un **XmlReadMode** explícito en lugar de permitir el uso del valor predeterminado **Auto**.|  
|**ReadSchema**|Lee cualquier esquema alineado y carga los datos y el esquema.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se agregan nuevas tablas del esquema alineado al esquema existente en el <xref:System.Data.DataSet>.  Si ya existe alguna tabla del esquema alineado en el <xref:System.Data.DataSet>, se iniciará una excepción.  No podrá modificar el esquema de una tabla existente mediante **XmlReadMode.ReadSchema**.<br /><br /> Si el <xref:System.Data.DataSet> no contiene un esquema y no hay ningún esquema alineado, no se leerá ningún dato.<br /><br /> Es posible definir el esquema alineado mediante el esquema del lenguaje de definición de esquemas XML \(XSD\).  Para obtener información detallada sobre cómo escribir esquemas alineados como esquemas XML, vea [Derivar la estructura relacional de DataSet desde la definición de esquema XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Pasa por alto cualquier esquema alineado y carga los datos en el esquema del <xref:System.Data.DataSet> existente.  Se descartan todos los datos que no coincidan con el esquema existente.  Si no existe ningún esquema en el <xref:System.Data.DataSet>, no se cargará ningún dato.<br /><br /> Si los datos son un DiffGram, **IgnoreSchema** tiene la misma funcionalidad que **DiffGram** *.*|  
|**InferSchema**|Pasa por alto cualquier esquema alineado, deduce el esquema por la estructura de los datos XML y, a continuación, carga los datos.<br /><br /> Si el <xref:System.Data.DataSet> ya contiene un esquema, se extiende el esquema actual mediante la adición de columnas a las tablas existentes.  Si no existen tablas, no se agregarán tablas adicionales.  Se iniciará una excepción si ya existe una tabla inferida con un espacio de nombres diferente o si alguna columna inferida entra en conflicto con columnas existentes.<br /><br /> Para obtener información detallada sobre cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Lee un DiffGram y agrega los datos al esquema actual.  **DiffGram** combina las filas nuevas con las filas existentes en las que coinciden los valores de identificador.  Vea "Combinar datos desde XML" al final de este tema.  Para obtener más información sobre DiffGrams, vea [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Fragmento**|Sigue leyendo varios fragmentos de XML hasta llegar al final de la secuencia.  Los fragmentos que coinciden con el esquema del <xref:System.Data.DataSet> se anexan a las tablas apropiadas.  Los fragmentos que no coinciden con el esquema del <xref:System.Data.DataSet> se descartan.|  
  
> [!NOTE]
>  Si pasa un **XmlReader** a un **ReadXml** que se encuentra en medio de un documento XML, **ReadXml** leerá hasta el siguiente nodo de elemento y lo considerará un elemento raíz, leyendo hasta el final del nodo de elemento únicamente.  Esto no se aplica si especifica **XmlReadMode.Fragment**.  
  
## Entidades DTD  
 Si el código XML contiene entidades definidas en un esquema de definición de tipo de documento \(DTD\), se iniciará una excepción si intenta cargar un <xref:System.Data.DataSet> pasando a **ReadXml** un nombre de archivo, una secuencia o un **XmlReader** sin validación.  En su lugar, debe crear un **XmlValidatingReader**, donde **EntityHandling** tenga el valor **EntityHandling.ExpandEntities**, y pasar el **XmlValidatingReader** a **ReadXml**.  El **XmlValidatingReader** expandirá las entidades antes de que las lea el <xref:System.Data.DataSet>.  
  
 En los siguientes ejemplos de código se muestra cómo cargar un <xref:System.Data.DataSet> desde una secuencia XML.  En el primer ejemplo se muestra un nombre de archivo que se pasa al método **ReadXml**.  En el segundo ejemplo se muestra una cadena que contiene el código XML que se carga mediante un <xref:System.IO.StringReader>.  
  
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
>  Si llama a **ReadXml** para cargar un archivo muy grande, el rendimiento puede resultar muy lento.  Para garantizar un rendimiento óptimo de **ReadXml** \(en un archivo de gran tamaño\) llame al método <xref:System.Data.DataTable.BeginLoadData%2A> para cada una de las tablas del <xref:System.Data.DataSet>y, a continuación, llame a **ReadXml**.  Por último, llame a <xref:System.Data.DataTable.EndLoadData%2A> para cada una de las tablas del <xref:System.Data.DataSet>, tal y como se muestra en el siguiente ejemplo.  
  
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
>  Si el esquema XSD de un <xref:System.Data.DataSet> incluye un **targetNamespace**, no se podrán leer los datos y pueden aparecer excepciones al llamar a **ReadXml** para cargar el <xref:System.Data.DataSet> con XML que contenga elementos con un espacio de nombres sin calificar.  En este caso, para leer los elementos no calificados, establezca **elementFormDefault** en "completo" en el esquema XSD.  Por ejemplo:  
  
```  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## Combinar datos a partir de XML  
 Si el <xref:System.Data.DataSet> ya contiene datos, los nuevos datos procedentes del código XML se agregarán a los ya presentes en el <xref:System.Data.DataSet>.  **ReadXml** no combina a partir de XML en el <xref:System.Data.DataSet> ninguna información de fila que tenga claves principales coincidentes.  Si desea sobrescribir información de fila existente con nueva información procedente de XML, utilice **ReadXml** para crear un nuevo<xref:System.Data.DataSet> y, a continuación, realice una operación <xref:System.Data.DataSet.Merge%2A> el nuevo <xref:System.Data.DataSet> en el <xref:System.Data.DataSet> existente.  Hay que tener en cuenta que al cargar un DiffGram mediante un **ReadXML** cuyo valor de **XmlReadMode** es **DiffGram** se combinarán las filas que tengan el mismo identificador único.  
  
## Vea también  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=fullName>   
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)   
 [Derivar la estructura relacional de DataSet desde la definición de esquema XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)