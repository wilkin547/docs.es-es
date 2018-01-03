---
title: "Sincronización de DataSet y XmlDataDocument"
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
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: acc68fd36d2887e5e951f9ba5adc20e8cfd87fd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="6f14d-102">Sincronización de DataSet y XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="6f14d-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="6f14d-103">El <xref:System.Data.DataSet> de ADO.NET proporciona una representación relacional de datos.</span><span class="sxs-lookup"><span data-stu-id="6f14d-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="6f14d-104">Para el acceso a datos jerárquicos puede utilizar las clases XML disponibles en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f14d-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="6f14d-105">Históricamente, estas dos representaciones de datos se han utilizado independientemente.</span><span class="sxs-lookup"><span data-stu-id="6f14d-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="6f14d-106">Sin embargo, .NET Framework permite el acceso sincrónico en tiempo real a las representaciones relacionales y jerárquicas de los datos mediante la **conjunto de datos** objeto y el <xref:System.Xml.XmlDataDocument> objeto, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6f14d-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="6f14d-107">Cuando un **conjunto de datos** está sincronizado con un **XmlDataDocument**, ambos objetos trabajan con un único conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="6f14d-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="6f14d-108">Esto significa que si se realiza un cambio en el **conjunto de datos**, el cambio se reflejará en la **XmlDataDocument**y viceversa.</span><span class="sxs-lookup"><span data-stu-id="6f14d-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="6f14d-109">La relación entre el **conjunto de datos** y **XmlDataDocument** crea gran flexibilidad al permitir que una sola aplicación, mediante un único conjunto de datos, para tener acceso a todo el conjunto de servicios integrados alrededor de la **conjunto de datos** (como controles de formularios Web Forms y formularios Windows Forms y diseñadores de Visual Studio. NET), así como el conjunto de servicios XML como Extensible Stylesheet Language (XSL), las transformaciones XSL (XSLT) y ruta de acceso de XML Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="6f14d-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="6f14d-110">No tiene que elegir el conjunto de servicios a los que desea dirigir la aplicación, ya que ambos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="6f14d-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="6f14d-111">Hay varias formas de sincronizar un **conjunto de datos** con una **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="6f14d-112">Puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f14d-112">You can:</span></span>  
  
-   <span data-ttu-id="6f14d-113">Rellenar un **conjunto de datos** con esquema (es decir, una estructura relacional) y los datos y, a continuación, sincronizarlo con un nuevo **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="6f14d-114">Esto ofrece una vista jerárquica de los datos relacionales existentes.</span><span class="sxs-lookup"><span data-stu-id="6f14d-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="6f14d-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6f14d-115">For example:</span></span>  
  
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
  
-   <span data-ttu-id="6f14d-116">Rellenar un **conjunto de datos** con el esquema únicamente (como fuertemente tipado **conjunto de datos**), sincronizarlo con un **XmlDataDocument**y, a continuación, cargue el  **XmlDataDocument** desde un documento XML.</span><span class="sxs-lookup"><span data-stu-id="6f14d-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="6f14d-117">Esto ofrece una vista relacional de los datos jerárquicos existentes.</span><span class="sxs-lookup"><span data-stu-id="6f14d-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="6f14d-118">Los nombres de tabla y columna en la **conjunto de datos** esquema debe coincidir con los nombres de los elementos XML que desea sincronizarlos.</span><span class="sxs-lookup"><span data-stu-id="6f14d-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="6f14d-119">La coincidencia distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6f14d-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="6f14d-120">Tenga en cuenta que el esquema de la **conjunto de datos** solo debe coincidir con los elementos XML que desea exponer en la vista relacional.</span><span class="sxs-lookup"><span data-stu-id="6f14d-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="6f14d-121">De esta forma puede tener un documento XML muy grande y una "ventana" relacional muy pequeña de ese documento.</span><span class="sxs-lookup"><span data-stu-id="6f14d-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="6f14d-122">El **XmlDataDocument** conserva todo el documento XML, aunque la **conjunto de datos** sólo exponga una pequeña parte de ella.</span><span class="sxs-lookup"><span data-stu-id="6f14d-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="6f14d-123">(Para obtener un ejemplo detallado, vea [sincronizar DataSet con XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="6f14d-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="6f14d-124">En el ejemplo de código siguiente se muestra los pasos para crear un **conjunto de datos** y llenar su esquema, a continuación, sincronizarlo con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="6f14d-125">Tenga en cuenta que la **conjunto de datos** esquema sólo es necesario que coincidan los elementos de la **XmlDataDocument** que desea exponer mediante la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="6f14d-126">No se puede cargar un **XmlDataDocument** si está sincronizado con un **conjunto de datos** que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="6f14d-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="6f14d-127">Se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="6f14d-127">An exception will be thrown.</span></span>  
  
-   <span data-ttu-id="6f14d-128">Crear un nuevo **XmlDataDocument** y cargarlo desde un documento XML y, a continuación, obtener acceso a la vista relacional de los datos mediante la **conjunto de datos** propiedad de la **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="6f14d-129">Debe establecer el esquema de la **conjunto de datos** antes de poder ver cualquiera de los datos de la **XmlDataDocument** mediante la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="6f14d-130">Una vez más, los nombres de tabla y columna de nombres de su **conjunto de datos** esquema debe coincidir con los nombres de los elementos XML que desea sincronizarlos.</span><span class="sxs-lookup"><span data-stu-id="6f14d-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="6f14d-131">La coincidencia distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6f14d-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="6f14d-132">En el ejemplo de código siguiente se muestra cómo obtener acceso a la vista relacional de los datos en un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="6f14d-133">Otra ventaja de sincronizar un **XmlDataDocument** con un **conjunto de datos** es que se conserva la fidelidad de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="6f14d-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="6f14d-134">Si el **conjunto de datos** se rellena a partir de un documento XML mediante **ReadXml**, cuando los datos se vuelvan a escribir como un documento XML mediante **WriteXml** pueden diferir considerablemente de la documento XML original.</span><span class="sxs-lookup"><span data-stu-id="6f14d-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="6f14d-135">Esto es porque el **conjunto de datos** no conserva el formato, como el espacio en blanco o información jerárquica, como el orden de los elementos del documento XML.</span><span class="sxs-lookup"><span data-stu-id="6f14d-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="6f14d-136">El **conjunto de datos** no contiene elementos del documento XML que se omitieron porque no coincidían con el esquema de la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="6f14d-137">Sincronizar un **XmlDataDocument** con un **conjunto de datos** permite que la estructura de elemento de formato y jerárquica del documento XML original se mantenga en el **XmlDataDocument**, mientras que la **conjunto de datos** contiene únicamente información de esquema y los datos apropiados para el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="6f14d-138">Al sincronizar un **conjunto de datos** con una **XmlDataDocument**, los resultados pueden diferir dependiendo de si o no su <xref:System.Data.DataRelation> objetos están anidados.</span><span class="sxs-lookup"><span data-stu-id="6f14d-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="6f14d-139">Para obtener más información, consulte [anidar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="6f14d-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f14d-140">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6f14d-140">In This Section</span></span>  
 [<span data-ttu-id="6f14d-141">Sincronización de un objeto DataSet con un objeto XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="6f14d-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="6f14d-142">Muestra cómo sincronizar un fuertemente tipado **conjunto de datos**, con un esquema mínimo con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="6f14d-143">Realización de una consulta XPath en un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="6f14d-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="6f14d-144">Muestra cómo realizar una consulta XPath en el contenido de un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="6f14d-145">Aplicación de una transformación XSL a un DataSet</span><span class="sxs-lookup"><span data-stu-id="6f14d-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="6f14d-146">Muestra cómo aplicar una transformación XSLT al contenido de un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="6f14d-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6f14d-147">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6f14d-147">Related Sections</span></span>  
 [<span data-ttu-id="6f14d-148">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="6f14d-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="6f14d-149">Describe cómo el **conjunto de datos** interactúa con XML como origen de datos, como cargar y hacer persistente el contenido de un **conjunto de datos** como datos XML.</span><span class="sxs-lookup"><span data-stu-id="6f14d-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="6f14d-150">Anidado de objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="6f14d-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="6f14d-151">Explica la importancia de anidada **DataRelation** objetos al representar el contenido de un **conjunto de datos** como datos XML y describe cómo crear estas relaciones.</span><span class="sxs-lookup"><span data-stu-id="6f14d-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="6f14d-152">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="6f14d-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="6f14d-153">Describe la **conjunto de datos** y cómo utilizarlo para administrar datos de aplicación e interactuar con orígenes de datos como bases de datos relacionales y XML.</span><span class="sxs-lookup"><span data-stu-id="6f14d-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="6f14d-154">Contiene información de referencia sobre la **XmlDataDocument** clase.</span><span class="sxs-lookup"><span data-stu-id="6f14d-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f14d-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f14d-155">See Also</span></span>  
 [<span data-ttu-id="6f14d-156">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="6f14d-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
