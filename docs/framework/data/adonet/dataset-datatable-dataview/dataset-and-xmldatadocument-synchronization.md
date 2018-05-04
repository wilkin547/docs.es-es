---
title: Sincronización de DataSet y XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: cb16d4fae5dc153361fe2cb31cfd6af9b4b83c68
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>Sincronización de DataSet y XmlDataDocument
El <xref:System.Data.DataSet> de ADO.NET proporciona una representación relacional de datos. Para el acceso a datos jerárquicos puede utilizar las clases XML disponibles en .NET Framework. Históricamente, estas dos representaciones de datos se han utilizado independientemente. Sin embargo, .NET Framework permite el acceso sincrónico en tiempo real a las representaciones relacionales y jerárquicas de los datos mediante la **conjunto de datos** objeto y el <xref:System.Xml.XmlDataDocument> objeto, respectivamente.  
  
 Cuando un **conjunto de datos** está sincronizado con un **XmlDataDocument**, ambos objetos trabajan con un único conjunto de datos. Esto significa que si se realiza un cambio en el **conjunto de datos**, el cambio se reflejará en la **XmlDataDocument**y viceversa. La relación entre el **conjunto de datos** y **XmlDataDocument** crea gran flexibilidad al permitir que una sola aplicación, mediante un único conjunto de datos, para tener acceso a todo el conjunto de servicios integrados alrededor de la **conjunto de datos** (como controles de formularios Web Forms y formularios Windows Forms y diseñadores de Visual Studio. NET), así como el conjunto de servicios XML como Extensible Stylesheet Language (XSL), las transformaciones XSL (XSLT) y ruta de acceso de XML Language (XPath). No tiene que elegir el conjunto de servicios a los que desea dirigir la aplicación, ya que ambos están disponibles.  
  
 Hay varias formas de sincronizar un **conjunto de datos** con una **XmlDataDocument**. Puede realizar lo siguiente:  
  
-   Rellenar un **conjunto de datos** con esquema (es decir, una estructura relacional) y los datos y, a continuación, sincronizarlo con un nuevo **XmlDataDocument**. Esto ofrece una vista jerárquica de los datos relacionales existentes. Por ejemplo:  
  
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
  
-   Rellenar un **conjunto de datos** con el esquema únicamente (como fuertemente tipado **conjunto de datos**), sincronizarlo con un **XmlDataDocument**y, a continuación, cargue el  **XmlDataDocument** desde un documento XML. Esto ofrece una vista relacional de los datos jerárquicos existentes. Los nombres de tabla y columna en la **conjunto de datos** esquema debe coincidir con los nombres de los elementos XML que desea sincronizarlos. La coincidencia distingue mayúsculas de minúsculas.  
  
     Tenga en cuenta que el esquema de la **conjunto de datos** solo debe coincidir con los elementos XML que desea exponer en la vista relacional. De esta forma puede tener un documento XML muy grande y una "ventana" relacional muy pequeña de ese documento. El **XmlDataDocument** conserva todo el documento XML, aunque la **conjunto de datos** sólo exponga una pequeña parte de ella. (Para obtener un ejemplo detallado, vea [sincronizar DataSet con XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     En el ejemplo de código siguiente se muestra los pasos para crear un **conjunto de datos** y llenar su esquema, a continuación, sincronizarlo con un **XmlDataDocument**. Tenga en cuenta que la **conjunto de datos** esquema sólo es necesario que coincidan los elementos de la **XmlDataDocument** que desea exponer mediante la **conjunto de datos**.  
  
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
  
     No se puede cargar un **XmlDataDocument** si está sincronizado con un **conjunto de datos** que contiene los datos. Se iniciará una excepción.  
  
-   Crear un nuevo **XmlDataDocument** y cargarlo desde un documento XML y, a continuación, obtener acceso a la vista relacional de los datos mediante la **conjunto de datos** propiedad de la **XmlDataDocument**. Debe establecer el esquema de la **conjunto de datos** antes de poder ver cualquiera de los datos de la **XmlDataDocument** mediante la **conjunto de datos**. Una vez más, los nombres de tabla y columna de nombres de su **conjunto de datos** esquema debe coincidir con los nombres de los elementos XML que desea sincronizarlos. La coincidencia distingue mayúsculas de minúsculas.  
  
     En el ejemplo de código siguiente se muestra cómo obtener acceso a la vista relacional de los datos en un **XmlDataDocument**.  
  
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
  
 Otra ventaja de sincronizar un **XmlDataDocument** con un **conjunto de datos** es que se conserva la fidelidad de un documento XML. Si el **conjunto de datos** se rellena a partir de un documento XML mediante **ReadXml**, cuando los datos se vuelvan a escribir como un documento XML mediante **WriteXml** pueden diferir considerablemente de la documento XML original. Esto es porque el **conjunto de datos** no conserva el formato, como el espacio en blanco o información jerárquica, como el orden de los elementos del documento XML. El **conjunto de datos** no contiene elementos del documento XML que se omitieron porque no coincidían con el esquema de la **conjunto de datos**. Sincronizar un **XmlDataDocument** con un **conjunto de datos** permite que la estructura de elemento de formato y jerárquica del documento XML original se mantenga en el **XmlDataDocument**, mientras que la **conjunto de datos** contiene únicamente información de esquema y los datos apropiados para el **conjunto de datos**.  
  
 Al sincronizar un **conjunto de datos** con una **XmlDataDocument**, los resultados pueden diferir dependiendo de si o no su <xref:System.Data.DataRelation> objetos están anidados. Para obtener más información, consulte [anidar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Sincronización de un objeto DataSet con un objeto XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Muestra cómo sincronizar un fuertemente tipado **conjunto de datos**, con un esquema mínimo con un **XmlDataDocument**.  
  
 [Realización de una consulta XPath en un objeto DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Muestra cómo realizar una consulta XPath en el contenido de un **conjunto de datos**.  
  
 [Aplicación de una transformación XSL a un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Muestra cómo aplicar una transformación XSLT al contenido de un **conjunto de datos**.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Describe cómo el **conjunto de datos** interactúa con XML como origen de datos, como cargar y hacer persistente el contenido de un **conjunto de datos** como datos XML.  
  
 [Anidado de objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Explica la importancia de anidada **DataRelation** objetos al representar el contenido de un **conjunto de datos** como datos XML y describe cómo crear estas relaciones.  
  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Describe la **conjunto de datos** y cómo utilizarlo para administrar datos de aplicación e interactuar con orígenes de datos como bases de datos relacionales y XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Contiene información de referencia sobre la **XmlDataDocument** clase.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
