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
ms.openlocfilehash: 1d17bb97811bb3a2ae979e5a05b8d39baf2b9c63
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="6d80d-102">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="6d80d-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="6d80d-103">Es posible crear el contenido de un <xref:System.Data.DataSet> de ADO.NET a partir de una secuencia o de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="6d80d-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="6d80d-104">Además, con .NET Framework se dispone de una gran flexibilidad sobre qué información se carga desde XML y cómo se crea el esquema o la estructura relacional del <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6d80d-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="6d80d-105">Para rellenar un <xref:System.Data.DataSet> con datos de XML, utilice el **ReadXml** método de la <xref:System.Data.DataSet> objeto.</span><span class="sxs-lookup"><span data-stu-id="6d80d-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="6d80d-106">El **ReadXml** método lee de un archivo, una secuencia, o un **XmlReader**y toma como argumentos el origen de XML y un elemento opcional **XmlReadMode** argumento.</span><span class="sxs-lookup"><span data-stu-id="6d80d-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="6d80d-107">(Para obtener más información sobre la **XmlReader**, consulte [NIB: leer datos de XML con XmlTextReader](http://msdn.microsoft.com/library/762c069b-b50c-41b8-936e-39eacfb0d540).) El **ReadXml** método lee el contenido de la secuencia XML o documentos y carga el <xref:System.Data.DataSet> con datos.</span><span class="sxs-lookup"><span data-stu-id="6d80d-107">(For more information about the **XmlReader**, see [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/library/762c069b-b50c-41b8-936e-39eacfb0d540).) The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="6d80d-108">También creará el esquema relacional de la <xref:System.Data.DataSet> en función de la **XmlReadMode** especificado y si ya existe un esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="6d80d-108">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="6d80d-109">En la tabla siguiente se describe las opciones para la **XmlReadMode** argumento.</span><span class="sxs-lookup"><span data-stu-id="6d80d-109">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="6d80d-110">Opción</span><span class="sxs-lookup"><span data-stu-id="6d80d-110">Option</span></span>|<span data-ttu-id="6d80d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d80d-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6d80d-112">**Auto**</span><span class="sxs-lookup"><span data-stu-id="6d80d-112">**Auto**</span></span>|<span data-ttu-id="6d80d-113">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6d80d-113">This is the default.</span></span> <span data-ttu-id="6d80d-114">Examina el código XML y elige la opción más apropiada, en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d80d-114">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="6d80d-115">-Si el XML es un DiffGram, **DiffGram** se utiliza.</span><span class="sxs-lookup"><span data-stu-id="6d80d-115">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="6d80d-116">-If el <xref:System.Data.DataSet> contiene un esquema o el código XML contiene un esquema insertado, **ReadSchema** se utiliza.</span><span class="sxs-lookup"><span data-stu-id="6d80d-116">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="6d80d-117">-If el <xref:System.Data.DataSet> no contiene un esquema y el código XML no contiene un esquema insertado, **InferSchema** se utiliza.</span><span class="sxs-lookup"><span data-stu-id="6d80d-117">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="6d80d-118">Si conoce el formato del XML que se está leyendo, para mejorar el rendimiento se recomienda establecer explícito **XmlReadMode**, en lugar de permitir el **automática** predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6d80d-118">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="6d80d-119">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="6d80d-119">**ReadSchema**</span></span>|<span data-ttu-id="6d80d-120">Lee cualquier esquema alineado y carga los datos y el esquema.</span><span class="sxs-lookup"><span data-stu-id="6d80d-120">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="6d80d-121">Si el <xref:System.Data.DataSet> ya contiene un esquema, se agregan nuevas tablas del esquema alineado al esquema existente en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6d80d-121">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6d80d-122">Si ya existe alguna tabla del esquema alineado en el <xref:System.Data.DataSet>, se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="6d80d-122">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="6d80d-123">No podrá modificar el esquema de una tabla existente mediante **XmlReadMode.ReadSchema**.</span><span class="sxs-lookup"><span data-stu-id="6d80d-123">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="6d80d-124">Si el <xref:System.Data.DataSet> no contiene un esquema y no hay ningún esquema alineado, no se leerá ningún dato.</span><span class="sxs-lookup"><span data-stu-id="6d80d-124">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="6d80d-125">Es posible definir el esquema alineado mediante el esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="6d80d-125">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="6d80d-126">Para obtener más información acerca de cómo escribir el esquema en línea como esquema XML, vea [derivar estructura relacional de DataSet de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="6d80d-126">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="6d80d-127">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="6d80d-127">**IgnoreSchema**</span></span>|<span data-ttu-id="6d80d-128">Pasa por alto cualquier esquema alineado y carga los datos en el esquema del <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="6d80d-128">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="6d80d-129">Se descartan todos los datos que no coincidan con el esquema existente.</span><span class="sxs-lookup"><span data-stu-id="6d80d-129">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="6d80d-130">Si no existe ningún esquema en el <xref:System.Data.DataSet>, no se cargará ningún dato.</span><span class="sxs-lookup"><span data-stu-id="6d80d-130">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="6d80d-131">Si los datos son un DiffGram, **IgnoreSchema** tiene la misma funcionalidad que **DiffGram** *.*</span><span class="sxs-lookup"><span data-stu-id="6d80d-131">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="6d80d-132">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="6d80d-132">**InferSchema**</span></span>|<span data-ttu-id="6d80d-133">Pasa por alto cualquier esquema alineado, deduce el esquema por la estructura de los datos XML y, a continuación, carga los datos.</span><span class="sxs-lookup"><span data-stu-id="6d80d-133">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="6d80d-134">Si el <xref:System.Data.DataSet> ya contiene un esquema, se extiende el esquema actual mediante la adición de columnas a las tablas existentes.</span><span class="sxs-lookup"><span data-stu-id="6d80d-134">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="6d80d-135">Si no existen tablas, no se agregarán tablas adicionales.</span><span class="sxs-lookup"><span data-stu-id="6d80d-135">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="6d80d-136">Se iniciará una excepción si ya existe una tabla inferida con un espacio de nombres diferente o si alguna columna inferida entra en conflicto con columnas existentes.</span><span class="sxs-lookup"><span data-stu-id="6d80d-136">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="6d80d-137">Para obtener más información acerca de cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [deducir el conjunto de datos relacional estructura de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6d80d-137">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="6d80d-138">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="6d80d-138">**DiffGram**</span></span>|<span data-ttu-id="6d80d-139">Lee un DiffGram y agrega los datos al esquema actual.</span><span class="sxs-lookup"><span data-stu-id="6d80d-139">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="6d80d-140">**DiffGram** combina las filas nuevas con las filas existentes que coincidan con los valores de identificador único.</span><span class="sxs-lookup"><span data-stu-id="6d80d-140">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="6d80d-141">Vea "Combinar datos desde XML" al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="6d80d-141">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="6d80d-142">Para obtener más información acerca de los DiffGrams, vea [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="6d80d-142">For more information about DiffGrams, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
|<span data-ttu-id="6d80d-143">**Fragment**</span><span class="sxs-lookup"><span data-stu-id="6d80d-143">**Fragment**</span></span>|<span data-ttu-id="6d80d-144">Sigue leyendo varios fragmentos de XML hasta llegar al final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="6d80d-144">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="6d80d-145">Los fragmentos que coinciden con el esquema del <xref:System.Data.DataSet> se anexan a las tablas apropiadas.</span><span class="sxs-lookup"><span data-stu-id="6d80d-145">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="6d80d-146">Los fragmentos que no coinciden con el esquema del <xref:System.Data.DataSet> se descartan.</span><span class="sxs-lookup"><span data-stu-id="6d80d-146">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6d80d-147">Si se pasa un **XmlReader** a **ReadXml** decir posicionada parte de la forma en un documento XML, **ReadXml** leerá hasta el siguiente nodo de elemento y lo considerará la raíz elemento, leyendo hasta el final del nodo de elemento únicamente.</span><span class="sxs-lookup"><span data-stu-id="6d80d-147">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="6d80d-148">Esto no se aplica si especifica **XmlReadMode.Fragment**.</span><span class="sxs-lookup"><span data-stu-id="6d80d-148">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="6d80d-149">Entidades DTD</span><span class="sxs-lookup"><span data-stu-id="6d80d-149">DTD Entities</span></span>  
 <span data-ttu-id="6d80d-150">Si el código XML contiene entidades definidas en un esquema de definición (DTD) de tipo de documento, se producirá una excepción si intenta cargar un <xref:System.Data.DataSet> pasando un archivo de nombre, una secuencia o no validación **XmlReader** a  **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="6d80d-150">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="6d80d-151">En su lugar, debe crear un **XmlValidatingReader**, con **EntityHandling** establecido en **EntityHandling.ExpandEntities**y pase el  **XmlValidatingReader** a **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="6d80d-151">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="6d80d-152">El **XmlValidatingReader** expandirá las entidades antes de que se lea el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6d80d-152">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="6d80d-153">En los siguientes ejemplos de código se muestra cómo cargar un <xref:System.Data.DataSet> desde una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="6d80d-153">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="6d80d-154">El primer ejemplo muestra un nombre de archivo que se pasan a la **ReadXml** método.</span><span class="sxs-lookup"><span data-stu-id="6d80d-154">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="6d80d-155">En el segundo ejemplo se muestra una cadena que contiene el código XML que se carga mediante un <xref:System.IO.StringReader>.</span><span class="sxs-lookup"><span data-stu-id="6d80d-155">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
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
>  <span data-ttu-id="6d80d-156">Si se llama a **ReadXml** para cargar un archivo muy grande, puede encontrar un rendimiento lento.</span><span class="sxs-lookup"><span data-stu-id="6d80d-156">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="6d80d-157">Para garantizar un rendimiento óptimo con **ReadXml**, en un archivo grande, llame a la <xref:System.Data.DataTable.BeginLoadData%2A> método para cada tabla en la <xref:System.Data.DataSet>y, a continuación, llame a **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="6d80d-157">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="6d80d-158">Por último, llame a <xref:System.Data.DataTable.EndLoadData%2A> para cada una de las tablas del <xref:System.Data.DataSet>, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6d80d-158">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="6d80d-159">Si el esquema XSD para su <xref:System.Data.DataSet> incluye un **targetNamespace**, no se pueden leer los datos y pueden aparecer excepciones al llamar a **ReadXml** para cargar el <xref:System.Data.DataSet> con XML que contenga elementos con un espacio de nombres sin calificación.</span><span class="sxs-lookup"><span data-stu-id="6d80d-159">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="6d80d-160">Para leer elementos no calificados en este caso, establezca **elementFormDefault** igual a "qualified" en el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="6d80d-160">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="6d80d-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6d80d-161">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="6d80d-162">Combinar datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="6d80d-162">Merging Data from XML</span></span>  
 <span data-ttu-id="6d80d-163">Si el <xref:System.Data.DataSet> ya contiene datos, los nuevos datos procedentes del código XML se agregarán a los ya presentes en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6d80d-163">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6d80d-164">**ReadXml** no combina a partir de XML en el <xref:System.Data.DataSet> ninguna información con claves principales coincidentes de fila.</span><span class="sxs-lookup"><span data-stu-id="6d80d-164">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="6d80d-165">Para sobrescribir información de fila existente con nueva información procedente de XML, utilice **ReadXml** para crear un nuevo <xref:System.Data.DataSet>y, a continuación, <xref:System.Data.DataSet.Merge%2A> nuevo <xref:System.Data.DataSet> existentes <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6d80d-165">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6d80d-166">Tenga en cuenta que al cargar un DiffGram mediante **ReadXML** con una **XmlReadMode** de **DiffGram** se combinarán las filas que tienen el mismo identificador único.</span><span class="sxs-lookup"><span data-stu-id="6d80d-166">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d80d-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d80d-167">See Also</span></span>  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="6d80d-168">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="6d80d-168">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="6d80d-169">DiffGram</span><span class="sxs-lookup"><span data-stu-id="6d80d-169">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [<span data-ttu-id="6d80d-170">Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6d80d-170">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="6d80d-171">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="6d80d-171">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="6d80d-172">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="6d80d-172">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="6d80d-173">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="6d80d-173">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="6d80d-174">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="6d80d-174">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
