---
title: "Cargar la informaci&#243;n de esquema de DataSet desde XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Cargar la informaci&#243;n de esquema de DataSet desde XML
El esquema de un <xref:System.Data.DataSet> \(sus tablas, columnas, relaciones y restricciones\) se puede definir mediante programación, crear mediante los métodos **Fill** o **FillSchema** de un <xref:System.Data.Common.DataAdapter> o cargar desde un documento XML.  Para cargar información de esquema de un **DataSet** desde un documento XML puede utilizar el método **ReadXmlSchema** o **InferXmlSchema** del **DataSet**.  **ReadXmlSchema** permite cargar o deducir la información de esquema de un **DataSet** desde el documento que contiene el esquema de lenguaje de definición de esquema XML \(XSD\) o desde un documento XML con un esquema XML alineado.  **InferXmlSchema** le permite deducir el esquema a partir del documento XML y pasar por alto ciertos espacios de nombres XML que especifique.  
  
> [!NOTE]
>  Es posible que el orden de las tablas de un objeto **DataSet** no se conserve si usa servicios Web o serialización XML para transferir un objeto **DataSet** creado en memoria mediante construcciones XSD \(como las relaciones anidadas\).  Por tanto, en este caso el destinatario del objeto **DataSet** no debe depender del orden de las tablas.  Sin embargo, el orden de las tablas siempre se mantiene si el esquema del objeto **DataSet** que se transfiere se recupera de archivos XSD, en lugar de crearse en memoria.  
  
## ReadXmlSchema  
 Para cargar el esquema de un **DataSet** desde un documento XML sin cargar ningún dato, puede utilizar el método **ReadXmlSchema** del **DataSet**.  **ReadXmlSchema** crea el esquema del **DataSet** definido mediante el esquema del lenguaje de definición de esquemas XML \(XSD\).  
  
 El método **ReadXmlSchema** toma un único argumento, que puede ser un nombre de archivo, una secuencia o un **XmlReader** que contiene el documento XML que se va a cargar.  El documento XML puede contener únicamente el esquema o puede contener el esquema alineado con elementos XML que contienen datos.  Para obtener información detallada sobre cómo escribir esquemas alineados como esquemas XML, vea [Derivar la estructura relacional de DataSet desde la definición de esquema XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Si el documento XML pasado a **ReadXmlSchema** no contiene información de esquema alineado, **ReadXmlSchema** deducirá el esquema a partir de los elementos del documento XML.  Si el objeto **DataSet** ya contiene un esquema, se agregarán nuevas tablas si no existen ya para extender el esquema actual.  En las tablas existentes no se agregarán nuevas columnas.  Si una columna que se va a agregar ya existe en el **DataSet** pero tiene un tipo incompatible con la columna encontrada en el código XML, se iniciará una excepción.  Para obtener información detallada sobre cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Mientras que **ReadXmlSchema** carga o deduce únicamente el esquema de un **DataSet**, el método **ReadXml** del **DataSet** carga o deduce el esquema y los datos contenidos en el documento XML.  Para obtener más información, consulta [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 En los siguientes ejemplos de código se muestra cómo cargar el esquema de un **DataSet** desde un documento o una secuencia XML.  En el primer ejemplo se muestra cómo se pasa un nombre de archivo de esquema XML al método **ReadXmlSchema**.  En el segundo ejemplo se muestra un objeto **System.IO.StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## InferXmlSchema  
 También puede indicar al **DataSet** que deduzca su esquema a partir de un documento XML mediante el método **InferXmlSchema** del **DataSet**.  **InferXmlSchema** funciona del mismo modo que **ReadXml** con un **XmlReadMode** de **InferSchema** \(carga datos y deduce el esquema\) y **ReadXmlSchema** si el documento que se lee no contiene ningún esquema alineado.  Sin embargo, **InferXmlSchema** ofrece la posibilidad adicional de especificar que se pasen por alto determinados espacios de nombres XML cuando se deduzca el esquema.  **InferXmlSchema** acepta dos argumentos necesarios:la ubicación del documento XML \(especificada por un nombre de archivo, una secuencia o un **XmlReader**\) y una matriz de cadena de espacios de nombres XML que la operación debe pasar por alto.  
  
 Por ejemplo, tomemos el siguiente código XML:  
  
```  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>   
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>   
  <Description od:adotype="203">Soft drinks and teas</Description>   
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>   
  <ReorderLevel od:adotype="3">10</ReorderLevel>   
  <Discontinued od:adotype="11">0</Discontinued>   
</Products>  
</NewDataSet>  
```  
  
 Debido a los atributos especificados para los elementos en el documento XML anterior, tanto el método **ReadXmlSchema** como **ReadXml** con un **XmlReadMode** de **InferSchema** crean tablas para todos los elementos del documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel** y **Discontinued**.  \(Para obtener más información, vea [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)\). Sin embargo, una estructura más adecuada consistiría en crear únicamente las tablas **Categories** y **Products** y, a continuación, crea las columnas **CategoryID**, **CategoryName** y **Description** en la tabla **Categories** y las columnas **ProductID**, **ReorderLevel** y **Discontinued** en la tabla **Products**.  Para asegurarse de que el esquema inferido pasa por alto los atributos especificados en los elementos XML, utilice el método **InferXmlSchema** y especifique que se debe pasar por alto el espacio de nombres XML para **officedata**, como se muestra en el siguiente ejemplo.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## Vea también  
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Derivar la estructura relacional de DataSet desde la definición de esquema XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)