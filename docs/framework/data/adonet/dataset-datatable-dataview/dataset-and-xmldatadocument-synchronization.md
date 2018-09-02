---
title: Sincronización de DataSet y XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 54991234d4eaa9edab218d3b0d221a6e477d2be5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43420108"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>Sincronización de DataSet y XmlDataDocument
El <xref:System.Data.DataSet> de ADO.NET proporciona una representación relacional de datos. Para el acceso a datos jerárquicos puede utilizar las clases XML disponibles en .NET Framework. Históricamente, estas dos representaciones de datos se han utilizado independientemente. Sin embargo, .NET Framework permite el acceso sincrónico en tiempo real a las representaciones relacionales y jerárquicas de los datos a través de la **DataSet** objeto y el <xref:System.Xml.XmlDataDocument> objeto, respectivamente.  
  
 Cuando un **DataSet** se sincroniza con un **XmlDataDocument**, ambos objetos trabajan con un único conjunto de datos. Esto significa que si se realiza un cambio en el **DataSet**, el cambio se reflejará en el **XmlDataDocument**y viceversa. La relación entre el **DataSet** y **XmlDataDocument** crea gran flexibilidad al permitir que una sola aplicación, mediante un único conjunto de datos, para tener acceso a todo el conjunto de servicios integrados en torno a la **DataSet** (por ejemplo, los controles de formularios Web Forms y Windows Forms y diseñadores de Visual Studio. NET), así como el conjunto de servicios XML como XML Path, XSL Transformations (XSLT) y lenguaje de hojas de estilo Extensible (XSL) Language (XPath). No tiene que elegir el conjunto de servicios a los que desea dirigir la aplicación, ya que ambos están disponibles.  
  
 Hay varias formas que puede sincronizar un **DataSet** con un **XmlDataDocument**. Puede realizar lo siguiente:  
  
-   Rellenar un **DataSet** con el esquema (es decir, una estructura relacional) y los datos y, a continuación, sincronizarlo con un nuevo **XmlDataDocument**. Esto ofrece una vista jerárquica de los datos relacionales existentes. Por ejemplo:  
  
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
  
-   Rellenar un **DataSet** con solo esquema (como fuertemente tipado **conjunto de datos**), sincronizarlo con un **XmlDataDocument**y, a continuación, cargue el  **XmlDataDocument** desde un documento XML. Esto ofrece una vista relacional de los datos jerárquicos existentes. Los nombres de tabla y columna en su **DataSet** esquema debe coincidir con los nombres de los elementos XML que desea sincronizarlos. La coincidencia distingue mayúsculas de minúsculas.  
  
     Tenga en cuenta que el esquema de la **DataSet** sólo debe coincidir con los elementos XML que desea exponer en la vista relacional. De esta forma puede tener un documento XML muy grande y una "ventana" relacional muy pequeña de ese documento. El **XmlDataDocument** conserva todo el documento XML, aunque la **DataSet** expone sólo una pequeña parte de ella. (Para obtener un ejemplo detallado, consulte [sincronizar DataSet con XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     El ejemplo de código siguiente muestra los pasos para crear un **DataSet** y llenar su esquema y, después, sincronizarlo con un **XmlDataDocument**. Tenga en cuenta que el **DataSet** esquema sólo es necesario que coincidan los elementos de la **XmlDataDocument** que desee exponer mediante el **DataSet**.  
  
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
  
     No se puede cargar un **XmlDataDocument** si está sincronizado con un **DataSet** que contiene los datos. Se iniciará una excepción.  
  
-   Cree un nuevo **XmlDataDocument** cargarlo desde un documento XML y, a continuación, obtener acceso a la vista relacional de los datos mediante el **DataSet** propiedad de la **XmlDataDocument**. Deberá establecer el esquema de la **DataSet** antes de poder ver cualquiera de los datos en el **XmlDataDocument** mediante el **conjunto de datos**. De nuevo, los nombres de los nombres de tabla y columna en su **DataSet** esquema debe coincidir con los nombres de los elementos XML que desea sincronizarlos. La coincidencia distingue mayúsculas de minúsculas.  
  
     El ejemplo de código siguiente muestra cómo obtener acceso a la vista relacional de los datos en un **XmlDataDocument**.  
  
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
  
 Otra ventaja de sincronizar un **XmlDataDocument** con un **DataSet** es que se conserva la fidelidad de un documento XML. Si el **DataSet** se rellena a partir de un documento XML utilizando **ReadXml**, cuando los datos se escriben como un documento XML utilizando **WriteXml** pueden diferir considerablemente desde el documento XML original. Esto es porque el **DataSet** no conserva el formato, como un espacio en blanco o información jerárquica, como el orden de los elementos del documento XML. El **DataSet** también no contiene elementos del documento XML que se omitieron porque no coincidían con el esquema de la **Dataset**. Sincronizar un **XmlDataDocument** con un **DataSet** permite que la estructura de elementos de formato y jerárquico del documento XML original se mantenga en el **XmlDataDocument**, mientras el **DataSet** contiene sola información de esquema y los datos apropiados para el **DataSet**.  
  
 Al sincronizar un **DataSet** con un **XmlDataDocument**, los resultados pueden diferir dependiendo de si su <xref:System.Data.DataRelation> se anidan objetos. Para obtener más información, consulte [anidar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Sincronización de un objeto DataSet con un objeto XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Muestra cómo sincronizar un fuertemente tipado **DataSet**, con un esquema mínimo con un **XmlDataDocument**.  
  
 [Realización de una consulta XPath en un objeto DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Muestra cómo realizar una consulta XPath en el contenido de un **DataSet**.  
  
 [Aplicación de una transformación XSL a un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Muestra cómo aplicar una transformación XSLT al contenido de un **DataSet**.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Describe cómo el **DataSet** interactúa con XML como origen de datos, incluidas la carga y hacer persistente el contenido de un **DataSet** como datos XML.  
  
 [Anidado de objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Explica la importancia de anidada **DataRelation** objetos al representar el contenido de un **DataSet** como datos XML y se describe cómo crear estas relaciones.  
  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Describe el **DataSet** y cómo usarlo para administrar datos de aplicación e interactuar con orígenes de datos como bases de datos relacionales y XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Contiene información de referencia sobre la **XmlDataDocument** clase.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
