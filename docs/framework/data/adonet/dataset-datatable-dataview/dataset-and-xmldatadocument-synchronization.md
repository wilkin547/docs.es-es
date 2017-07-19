---
title: "Sincronizaci&#243;n de DataSet y XmlDataDocument | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Sincronizaci&#243;n de DataSet y XmlDataDocument
El <xref:System.Data.DataSet> de ADO.NET proporciona una representación relacional de datos.  Para el acceso a datos jerárquicos puede utilizar las clases XML disponibles en .NET Framework.  Históricamente, estas dos representaciones de datos se han utilizado independientemente.  Sin embargo, .NET Framework habilita el acceso sincrónico en tiempo real tanto a la representación relacional como a la representación jerárquica de los datos mediante los objetos **DataSet** y <xref:System.Xml.XmlDataDocument>, respectivamente.  
  
 Cuando un **DataSet** se sincroniza con un **XmlDataDocument**, ambos objetos trabajan con un único conjunto de datos.  Esto significa que si se realiza un cambio en el **DataSet**, dicho cambio quedará reflejado en el **XmlDataDocument**, y viceversa.  La relación entre el **DataSet** y el **XmlDataDocument** ofrece una gran flexibilidad, ya que permite que una única aplicación, utilizando un único conjunto de datos, tenga acceso a todo el conjunto de servicios existentes en el **DataSet** \(como controles de formularios Web Forms y Windows Forms, y diseñadores de Visual Studio .NET\), así como al conjunto de servicios XML, incluyendo XSL \(Extensible Stylesheet Language\), XSLT \(XSL Transformations\) y el lenguaje de rutas XML \(XPath\).  No tiene que elegir el conjunto de servicios a los que desea dirigir la aplicación, ya que ambos están disponibles.  
  
 Hay varias formas de sincronizar un **DataSet** con un **XmlDataDocument**.  Puede realizar lo siguiente:  
  
-   Llenar un **DataSet** con el esquema \(estructura relacional\) y los datos y, después, sincronizarlo con un nuevo **XmlDataDocument**.  Esto ofrece una vista jerárquica de los datos relacionales existentes.  Por ejemplo:  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
-   Llenar un **DataSet** con el esquema únicamente \(como un **DataSet** fuertemente tipado\), sincronizarlo con un **XmlDataDocument** y cargar el **XmlDataDocument** desde un documento XML.  Esto ofrece una vista relacional de los datos jerárquicos existentes.  Los nombres de tabla y de columna del esquema del **DataSet** deben coincidir con los nombres de los elementos XML con los que desea sincronizarlos.  La coincidencia distingue mayúsculas de minúsculas.  
  
     Hay que tener en cuenta que en el esquema del **DataSet** solo es necesario que coincidan los elementos XML que desee exponer en la vista relacional.  De esta forma puede tener un documento XML muy grande y una "ventana" relacional muy pequeña de ese documento.  El **XmlDataDocument** conserva todo el documento XML, incluso aunque el **DataSet** solo exponga una pequeña parte del mismo.  Para obtener un ejemplo detallado, consulte [Sincronizar DataSet con XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).  
  
     En el siguiente ejemplo de código se muestran los pasos para crear un **DataSet**, llenar su esquema y, a continuación, sincronizarlo con un **XmlDataDocument**.  Hay que tener en cuenta que en el esquema del **DataSet** solo es necesario que coincidan los elementos del **XmlDataDocument** que desee exponer mediante el **DataSet**.  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     No puede cargar un **XmlDataDocument** si está sincronizado con un **DataSet** que contiene datos.  Se iniciará una excepción.  
  
-   Crear un nuevo **XmlDataDocument**, cargarlo desde un documento XML y, a continuación, tener acceso a la vista relacional de los datos mediante la propiedad **DataSet** del **XmlDataDocument**.  Debe establecer el esquema del **DataSet** antes de poder ver cualquiera de los datos del **XmlDataDocument** mediante el **DataSet**.  Una vez más, los nombres de tabla y de columna del esquema del **DataSet** deben coincidir con los nombres de los elementos XML con los que desea sincronizarlos.  La coincidencia distingue mayúsculas de minúsculas.  
  
     En el siguiente ejemplo de código se muestra cómo tener acceso a la vista relacional de los datos de un **XmlDataDocument**.  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 Otra ventaja de sincronizar un **XmlDataDocument** con un **DataSet** es que se conserva la fidelidad de un documento XML.  Si el **DataSet** se llena desde un documento XML mediante **ReadXml**, cuando se vuelvan a escribir los datos como un documento XML mediante **WriteXml** pueden diferir considerablemente con respecto al documento XML original.  Esto se debe a que el **DataSet** no conserva el formato, como el espacio en blanco, ni la información jerárquica, como el orden de los elementos, del documento XML.  El **DataSet** tampoco contiene elementos del documento XML que se omitieron porque no coincidían con el esquema del **Dataset**.  La sincronización de un **XmlDataDocument** con un **DataSet** permite conservar el formato y la estructura jerárquica de los elementos del documento XML original en el **XmlDataDocument**, mientras que el **DataSet** solo contiene los datos y la información de esquema apropiados para el **DataSet**.  
  
 Al sincronizar un **DataSet** con un **XmlDataDocument**, los resultados obtenidos pueden diferir dependiendo de si los objetos <xref:System.Data.DataRelation> están o no anidados.  Para obtener más información, consulta [Anidar DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## En esta sección  
 [Sincronizar DataSet con XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Muestra cómo sincronizar un **DataSet** fuertemente tipado y un esquema mínimo con un **XmlDataDocument**.  
  
 [Realizar una consulta de XPath en DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Muestra cómo realizar una consulta XPath de los contenidos de un **DataSet**.  
  
 [Aplicar una transformación XSLT a un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Muestra cómo aplicar una transformación XSLT al contenido de un **DataSet**.  
  
## Secciones relacionadas  
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Describe cómo interactúa el **DataSet** con XML como origen de datos, incluyendo cómo cargar y hacer persistente el contenido de un **DataSet** como datos XML.  
  
 [Anidar DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Explica la importancia de los objetos **DataRelation** anidados al representar el contenido de un **DataSet** como datos XML y describe cómo crear estas relaciones.  
  
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Describe el **DataSet** y cómo utilizarlo para administrar datos de aplicación e interactuar con orígenes de datos, incluyendo bases de datos relacionales y XML.  
  
 [Clase XmlDataDocument](frlrfSystemXmlXmlDataDocumentClassTopic)  
 Contiene información de referencia sobre la clase **XmlDataDocument**.  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)