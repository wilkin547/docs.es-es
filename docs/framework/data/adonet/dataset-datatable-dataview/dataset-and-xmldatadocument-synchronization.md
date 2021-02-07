---
description: 'Más información sobre: sincronización de DataSet y XmlDataDocument'
title: Sincronización de DataSet y XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: c3bb1af305dfc319cb2c4783f4e4edc108e9d737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739565"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>Sincronización de DataSet y XmlDataDocument

El <xref:System.Data.DataSet> de ADO.NET proporciona una representación relacional de datos. Para el acceso a datos jerárquicos puede utilizar las clases XML disponibles en .NET Framework. Históricamente, estas dos representaciones de datos se han utilizado independientemente. Sin embargo, el .NET Framework habilita el acceso sincrónico en tiempo real a las representaciones relacionales y jerárquicas de los datos a través del objeto **DataSet** y del <xref:System.Xml.XmlDataDocument> objeto, respectivamente.  
  
 Cuando un **conjunto** de datos se sincroniza con un **XmlDataDocument**, ambos objetos trabajan con un solo conjunto de datos. Esto significa que si se realiza un cambio en el **conjunto de DataSet**, el cambio se reflejará en el **XmlDataDocument** y viceversa. La relación entre el **conjunto de DataSet** y el **XmlDataDocument** crea una gran flexibilidad al permitir una sola aplicación, usar un único conjunto de datos para tener acceso al conjunto completo de servicios creados en torno al **conjunto** de datos (como los formularios web forms y los controles de Windows Forms, y diseñadores de Visual Studio .net), así como el conjunto de servicios XML, incluidos el lenguaje de hojas de estilo extensible (XSL), las transformaciones XSL (XSLT) y XML Path Language (XPath). No tiene que elegir el conjunto de servicios a los que desea dirigir la aplicación, ya que ambos están disponibles.  
  
 Hay varias maneras de sincronizar un **DataSet** con un **XmlDataDocument**. Puede:  
  
- Rellene un **DataSet** con un esquema (es decir, una estructura relacional) y los datos y, a continuación, sincronícelo con un **XmlDataDocument** nuevo. Esto ofrece una vista jerárquica de los datos relacionales existentes. Por ejemplo:  
  
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
  
- Rellenar un **DataSet** solo con el esquema (por ejemplo, un conjunto de un **DataSet** fuertemente tipado), sincronizarlo con un **XmlDataDocument** y, a continuación, cargar el **XmlDataDocument** desde un documento XML. Esto ofrece una vista relacional de los datos jerárquicos existentes. Los nombres de tabla y de columna del esquema del **conjunto** de los mismos deben coincidir con los nombres de los elementos XML con los que desea sincronizarlos. La coincidencia distingue mayúsculas de minúsculas.  
  
     Tenga en cuenta que el esquema del **conjunto** de elementos solo debe coincidir con los elementos XML que desea exponer en la vista relacional. De esta forma puede tener un documento XML muy grande y una "ventana" relacional muy pequeña de ese documento. El **XmlDataDocument** conserva todo el documento XML, aunque el **conjunto** de documentos solo expone una pequeña parte del mismo. (Para obtener un ejemplo detallado de esto, vea [sincronizar un DataSet con un XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md)).  
  
     En el ejemplo de código siguiente se muestran los pasos para crear un **conjunto** de elementos y rellenar su esquema y, después, sincronizarlo con un **XmlDataDocument**. Tenga en cuenta que el esquema del **conjunto** de elementos solo debe coincidir con los elementos del **XmlDataDocument** que desee exponer mediante el **DataSet**.  
  
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
  
     No se puede cargar un **XmlDataDocument** si está sincronizado con un **conjunto** de datos que contiene datos. Se iniciará una excepción.  
  
- Cree un nuevo **XmlDataDocument** y cárguelo desde un documento XML y, a continuación, acceda a la vista relacional de los datos mediante la propiedad **DataSet** del **XmlDataDocument**. Debe establecer el esquema del **conjunto** de datos antes de poder ver cualquiera de los datos del **XmlDataDocument** mediante el **DataSet**. De nuevo, los nombres de tabla y de columna del esquema del **conjunto** de elementos deben coincidir con los nombres de los elementos XML con los que desea que se sincronicen. La coincidencia distingue mayúsculas de minúsculas.  
  
     En el ejemplo de código siguiente se muestra cómo obtener acceso a la vista relacional de los datos de un **XmlDataDocument**.  
  
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
  
 Otra ventaja de sincronizar un **XmlDataDocument** con un **DataSet** es que se conserva la fidelidad de un documento XML. Si el **conjunto** de datos se rellena a partir de un documento XML mediante **ReadXml**, cuando se vuelvan a escribir los datos como un documento XML mediante **WriteXml** puede diferir drásticamente del documento XML original. Esto se debe a que el **conjunto** de datos no mantiene el formato, como un espacio en blanco, o información jerárquica, como el orden de los elementos, del documento XML. El **DataSet** tampoco contiene elementos del documento XML que se omitieron porque no coincidían con el esquema del **conjunto de DataSet**. Sincronizar un **XmlDataDocument** con un **conjunto** de datos permite que el formato y la estructura jerárquica de los elementos del documento XML original se mantengan en el **XmlDataDocument**, mientras que el **conjunto** de datos solo contiene información sobre los datos y el esquema correspondientes al **conjunto** de datos.  
  
 Al sincronizar un **DataSet** con un **XmlDataDocument**, los resultados pueden diferir dependiendo de si los <xref:System.Data.DataRelation> objetos están anidados o no. Para obtener más información, consulte anidamiento de objetos [DataRelation](nesting-datarelations.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [Sincronizar un objeto DataSet con un objeto XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Muestra cómo sincronizar un **DataSet** fuertemente tipado, con un esquema mínimo, con un **XmlDataDocument**.  
  
 [Realizar una consulta XPath en un objeto DataSet](performing-an-xpath-query-on-a-dataset.md)  
 Muestra cómo realizar una consulta XPath en el contenido de un **conjunto de DataSet**.  
  
 [Aplicar una transformación XSL a un DataSet](applying-an-xslt-transform-to-a-dataset.md)  
 Muestra cómo aplicar una transformación XSLT al contenido de un **conjunto de DataSet**.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)  
 Describe cómo interactúa el **DataSet** con XML como origen de datos, incluida la carga y persistencia del contenido de un **DATASET** como datos XML.  
  
 [Anidar objetos DataRelation](nesting-datarelations.md)  
 Describe la importancia de los objetos **DataRelation** anidados al representar el contenido de un **DATASET** como datos XML y describe cómo crear estas relaciones.  
  
 [Objetos DataSet, DataTable y DataView](index.md)  
 Describe el **conjunto** de datos y cómo usarlo para administrar datos de aplicación e interactuar con orígenes de datos, como bases de datos relacionales y XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Contiene información de referencia sobre la clase **XmlDataDocument** .  
  
## <a name="see-also"></a>Vea también

- [Información general de ADO.NET](../ado-net-overview.md)
