---
title: Sincronización de DataSet y XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 2790f0a9edd5bfde96683e00725dd04555379adf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153305"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="a0ebc-102">Sincronización de DataSet y XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="a0ebc-102">DataSet and XmlDataDocument Synchronization</span></span>

<span data-ttu-id="a0ebc-103">El <xref:System.Data.DataSet> de ADO.NET proporciona una representación relacional de datos.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="a0ebc-104">Para el acceso a datos jerárquicos puede utilizar las clases XML disponibles en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="a0ebc-105">Históricamente, estas dos representaciones de datos se han utilizado independientemente.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="a0ebc-106">Sin embargo, el .NET Framework habilita el acceso sincrónico en tiempo real a las representaciones relacionales y jerárquicas de los datos a través del objeto **DataSet** y del <xref:System.Xml.XmlDataDocument> objeto, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="a0ebc-107">Cuando un **conjunto** de datos se sincroniza con un **XmlDataDocument**, ambos objetos trabajan con un solo conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="a0ebc-108">Esto significa que si se realiza un cambio en el **conjunto de DataSet**, el cambio se reflejará en el **XmlDataDocument**y viceversa.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="a0ebc-109">La relación entre el **conjunto de DataSet** y el **XmlDataDocument** crea una gran flexibilidad al permitir una sola aplicación, usar un único conjunto de datos para tener acceso al conjunto completo de servicios creados en torno al **conjunto** de datos (como los formularios web forms y los controles de Windows Forms, y diseñadores de Visual Studio .net), así como el conjunto de servicios XML, incluidos el lenguaje de hojas de estilo extensible (XSL), las transformaciones XSL (XSLT) y XML Path Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="a0ebc-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="a0ebc-110">No tiene que elegir el conjunto de servicios a los que desea dirigir la aplicación, ya que ambos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="a0ebc-111">Hay varias maneras de sincronizar un **DataSet** con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="a0ebc-112">Puede:</span><span class="sxs-lookup"><span data-stu-id="a0ebc-112">You can:</span></span>  
  
- <span data-ttu-id="a0ebc-113">Rellene un **DataSet** con un esquema (es decir, una estructura relacional) y los datos y, a continuación, sincronícelo con un **XmlDataDocument**nuevo.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="a0ebc-114">Esto ofrece una vista jerárquica de los datos relacionales existentes.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="a0ebc-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a0ebc-115">For example:</span></span>  
  
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
  
- <span data-ttu-id="a0ebc-116">Rellenar un **DataSet** solo con el esquema (por ejemplo, un conjunto de un **DataSet**fuertemente tipado), sincronizarlo con un **XmlDataDocument**y, a continuación, cargar el **XmlDataDocument** desde un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="a0ebc-117">Esto ofrece una vista relacional de los datos jerárquicos existentes.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="a0ebc-118">Los nombres de tabla y de columna del esquema del **conjunto** de los mismos deben coincidir con los nombres de los elementos XML con los que desea sincronizarlos.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="a0ebc-119">La coincidencia distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="a0ebc-120">Tenga en cuenta que el esquema del **conjunto** de elementos solo debe coincidir con los elementos XML que desea exponer en la vista relacional.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="a0ebc-121">De esta forma puede tener un documento XML muy grande y una "ventana" relacional muy pequeña de ese documento.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="a0ebc-122">El **XmlDataDocument** conserva todo el documento XML, aunque el **conjunto** de documentos solo expone una pequeña parte del mismo.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="a0ebc-123">(Para obtener un ejemplo detallado de esto, vea [sincronizar un DataSet con un XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md)).</span><span class="sxs-lookup"><span data-stu-id="a0ebc-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="a0ebc-124">En el ejemplo de código siguiente se muestran los pasos para crear un **conjunto** de elementos y rellenar su esquema y, después, sincronizarlo con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="a0ebc-125">Tenga en cuenta que el esquema del **conjunto** de elementos solo debe coincidir con los elementos del **XmlDataDocument** que desee exponer mediante el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="a0ebc-126">No se puede cargar un **XmlDataDocument** si está sincronizado con un **conjunto** de datos que contiene datos.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="a0ebc-127">Se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="a0ebc-128">Cree un nuevo **XmlDataDocument** y cárguelo desde un documento XML y, a continuación, acceda a la vista relacional de los datos mediante la propiedad **DataSet** del **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="a0ebc-129">Debe establecer el esquema del **conjunto** de datos antes de poder ver cualquiera de los datos del **XmlDataDocument** mediante el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="a0ebc-130">De nuevo, los nombres de tabla y de columna del esquema del **conjunto** de elementos deben coincidir con los nombres de los elementos XML con los que desea que se sincronicen.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="a0ebc-131">La coincidencia distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="a0ebc-132">En el ejemplo de código siguiente se muestra cómo obtener acceso a la vista relacional de los datos de un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="a0ebc-133">Otra ventaja de sincronizar un **XmlDataDocument** con un **DataSet** es que se conserva la fidelidad de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="a0ebc-134">Si el **conjunto** de datos se rellena a partir de un documento XML mediante **ReadXml**, cuando se vuelvan a escribir los datos como un documento XML mediante **WriteXml** puede diferir drásticamente del documento XML original.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="a0ebc-135">Esto se debe a que el **conjunto** de datos no mantiene el formato, como un espacio en blanco, o información jerárquica, como el orden de los elementos, del documento XML.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="a0ebc-136">El **DataSet** tampoco contiene elementos del documento XML que se omitieron porque no coincidían con el esquema del **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="a0ebc-137">Sincronizar un **XmlDataDocument** con un **conjunto** de datos permite que el formato y la estructura jerárquica de los elementos del documento XML original se mantengan en el **XmlDataDocument**, mientras que el **conjunto** de datos solo contiene información sobre los datos y el esquema correspondientes al **conjunto**de datos.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="a0ebc-138">Al sincronizar un **DataSet** con un **XmlDataDocument**, los resultados pueden diferir dependiendo de si los <xref:System.Data.DataRelation> objetos están anidados o no.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="a0ebc-139">Para obtener más información, consulte anidamiento de objetos [DataRelation](nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="a0ebc-139">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0ebc-140">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a0ebc-140">In This Section</span></span>  

 [<span data-ttu-id="a0ebc-141">Sincronizar un objeto DataSet con un objeto XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="a0ebc-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="a0ebc-142">Muestra cómo sincronizar un **DataSet**fuertemente tipado, con un esquema mínimo, con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="a0ebc-143">Realizar una consulta XPath en un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="a0ebc-143">Performing an XPath Query on a DataSet</span></span>](performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="a0ebc-144">Muestra cómo realizar una consulta XPath en el contenido de un **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="a0ebc-145">Aplicar una transformación XSL a un DataSet</span><span class="sxs-lookup"><span data-stu-id="a0ebc-145">Applying an XSLT Transform to a DataSet</span></span>](applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="a0ebc-146">Muestra cómo aplicar una transformación XSLT al contenido de un **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a0ebc-147">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a0ebc-147">Related Sections</span></span>  

 [<span data-ttu-id="a0ebc-148">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="a0ebc-148">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="a0ebc-149">Describe cómo interactúa el **DataSet** con XML como origen de datos, incluida la carga y persistencia del contenido de un **DATASET** como datos XML.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="a0ebc-150">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="a0ebc-150">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="a0ebc-151">Describe la importancia de los objetos **DataRelation** anidados al representar el contenido de un **DATASET** como datos XML y describe cómo crear estas relaciones.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="a0ebc-152">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="a0ebc-152">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="a0ebc-153">Describe el **conjunto** de datos y cómo usarlo para administrar datos de aplicación e interactuar con orígenes de datos, como bases de datos relacionales y XML.</span><span class="sxs-lookup"><span data-stu-id="a0ebc-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="a0ebc-154">Contiene información de referencia sobre la clase **XmlDataDocument** .</span><span class="sxs-lookup"><span data-stu-id="a0ebc-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ebc-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0ebc-155">See also</span></span>

- [<span data-ttu-id="a0ebc-156">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a0ebc-156">ADO.NET Overview</span></span>](../ado-net-overview.md)
