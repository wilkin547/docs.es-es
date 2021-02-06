---
description: Más información acerca de cómo cargar información de esquema de conjunto de datos desde XML
title: Cargar información del esquema de un conjunto de datos desde XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: dd3a327270d6f8e3086d7206dd6f44290415c55e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652112"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="e48cc-103">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="e48cc-103">Loading DataSet Schema Information from XML</span></span>

<span data-ttu-id="e48cc-104">El esquema de un <xref:System.Data.DataSet> (sus tablas, columnas, relaciones y restricciones) se puede definir mediante programación, lo crean los métodos **Fill** o **FillSchema** de un <xref:System.Data.Common.DataAdapter> , o se cargan desde un documento XML.</span><span class="sxs-lookup"><span data-stu-id="e48cc-104">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="e48cc-105">Para cargar información de esquema de **conjunto** de datos desde un documento XML, puede usar los métodos **ReadXmlSchema** o **InferXmlSchema** del **conjunto** de datos.</span><span class="sxs-lookup"><span data-stu-id="e48cc-105">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="e48cc-106">**ReadXmlSchema** permite cargar o deducir información del esquema del **conjunto** de datos del documento que contiene el esquema del lenguaje de definición de esquemas XML (XSD) o un documento XML con un esquema XML alineado.</span><span class="sxs-lookup"><span data-stu-id="e48cc-106">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="e48cc-107">**InferXmlSchema** permite deducir el esquema del documento XML mientras se omiten determinados espacios de nombres XML que se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="e48cc-107">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e48cc-108">Es posible que el orden de las tablas en un **conjunto** de objetos no se conserve cuando se utilizan los servicios web o la serialización XML para transferir un **DataSet** que se creó en memoria mediante construcciones xsd (como las relaciones anidadas).</span><span class="sxs-lookup"><span data-stu-id="e48cc-108">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="e48cc-109">Por lo tanto, el destinatario del **conjunto de DataSet** no debe depender de la ordenación de la tabla en este caso.</span><span class="sxs-lookup"><span data-stu-id="e48cc-109">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="e48cc-110">Sin embargo, el orden de las tablas siempre se conserva si el esquema del conjunto de los **conjuntos** de archivos que se va a transferir se leyó desde archivos XSD, en lugar de crearse en memoria.</span><span class="sxs-lookup"><span data-stu-id="e48cc-110">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="e48cc-111">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="e48cc-111">ReadXmlSchema</span></span>  

 <span data-ttu-id="e48cc-112">Para cargar el esquema de un **DataSet** desde un documento XML sin cargar ningún dato, puede usar el método **ReadXmlSchema** del **conjunto** de datos.</span><span class="sxs-lookup"><span data-stu-id="e48cc-112">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="e48cc-113">**ReadXmlSchema** crea un esquema de **conjunto de DataSet** definido mediante el esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="e48cc-113">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="e48cc-114">El método **ReadXmlSchema** toma un solo argumento de un nombre de archivo, una secuencia o un **XmlReader** que contiene el documento XML que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="e48cc-114">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="e48cc-115">El documento XML puede contener únicamente el esquema o puede contener el esquema alineado con elementos XML que contienen datos.</span><span class="sxs-lookup"><span data-stu-id="e48cc-115">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="e48cc-116">Para obtener más información sobre cómo escribir esquemas insertados como esquemas XML, vea [derivar una estructura relacional de conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="e48cc-116">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="e48cc-117">Si el documento XML pasado a **ReadXmlSchema** no contiene información de esquema insertado, **ReadXmlSchema** deducirá el esquema a partir de los elementos del documento XML.</span><span class="sxs-lookup"><span data-stu-id="e48cc-117">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="e48cc-118">Si el **conjunto** de contenido ya contiene un esquema, el esquema actual se extenderá agregando nuevas tablas si aún no existen.</span><span class="sxs-lookup"><span data-stu-id="e48cc-118">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="e48cc-119">En las tablas existentes no se agregarán nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="e48cc-119">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="e48cc-120">Si una columna que se va a agregar ya existe en el **conjunto de DataSet** pero tiene un tipo incompatible con la columna que se encuentra en el XML, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="e48cc-120">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="e48cc-121">Para obtener más información sobre cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [inferir la estructura relacional de DataSet desde XML](inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e48cc-121">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="e48cc-122">Aunque **ReadXmlSchema** carga o deduce solo el esquema de un **DataSet**, el método **ReadXml** del **conjunto** de datos carga o deduce el esquema y los datos contenidos en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="e48cc-122">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="e48cc-123">Para obtener más información, vea [cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e48cc-123">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="e48cc-124">En los siguientes ejemplos de código se muestra cómo cargar un esquema de **DataSet** desde un documento o una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="e48cc-124">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="e48cc-125">En el primer ejemplo se muestra un nombre de archivo de esquema XML que se pasa al método **ReadXmlSchema** .</span><span class="sxs-lookup"><span data-stu-id="e48cc-125">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="e48cc-126">En el segundo ejemplo se muestra **System. IO. StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="e48cc-126">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="e48cc-127">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="e48cc-127">InferXmlSchema</span></span>  

 <span data-ttu-id="e48cc-128">También puede indicar al **conjunto de DataSet** que infiera su esquema a partir de un documento XML mediante el método **InferXmlSchema** del **conjunto** de información.</span><span class="sxs-lookup"><span data-stu-id="e48cc-128">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="e48cc-129">**InferXmlSchema** funciona igual que los dos **ReadXml** con un **XmlReadMode** de **InferSchema** (carga los datos, así como deduces) y **ReadXmlSchema** si el documento que se lee no contiene ningún esquema en línea.</span><span class="sxs-lookup"><span data-stu-id="e48cc-129">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="e48cc-130">Sin embargo, **InferXmlSchema** proporciona la capacidad adicional de permitirle especificar espacios de nombres XML determinados que se omitirán cuando se infiera el esquema.</span><span class="sxs-lookup"><span data-stu-id="e48cc-130">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="e48cc-131">**InferXmlSchema** acepta dos argumentos necesarios: la ubicación del documento XML, especificada por un nombre de archivo, una secuencia o un **XmlReader**; y una matriz de cadena de espacios de nombres XML que la operación pasará por alto.</span><span class="sxs-lookup"><span data-stu-id="e48cc-131">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="e48cc-132">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="e48cc-132">For example, consider the following XML:</span></span>  
  
```xml  
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
  
 <span data-ttu-id="e48cc-133">Debido a los atributos especificados para los elementos del documento XML anterior, tanto el método **ReadXmlSchema** como el **método ReadXml** con un **XmlReadMode** de **InferSchema** crearán tablas para cada elemento del documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel** y **Discontinued**.</span><span class="sxs-lookup"><span data-stu-id="e48cc-133">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="e48cc-134">(Para obtener más información, vea [inferir la estructura relacional de DataSet desde XML](inferring-dataset-relational-structure-from-xml.md)). Sin embargo, una estructura más adecuada consistiría en crear únicamente las tablas **Categories** y **Products** y, a continuación, crear las columnas **CategoryID**, **CategoryName** y **Description** en la tabla **Categories** y las columnas **ProductID**, **ReorderLevel** y **Discontinued** en la tabla **Products** .</span><span class="sxs-lookup"><span data-stu-id="e48cc-134">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="e48cc-135">Para asegurarse de que el esquema deducido omite los atributos especificados en los elementos XML, use el método **InferXmlSchema** y especifique el espacio de nombres XML para **officedata** que se va a omitir, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e48cc-135">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="e48cc-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e48cc-136">See also</span></span>

- [<span data-ttu-id="e48cc-137">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="e48cc-137">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="e48cc-138">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="e48cc-138">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="e48cc-139">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="e48cc-139">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="e48cc-140">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="e48cc-140">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="e48cc-141">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="e48cc-141">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="e48cc-142">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e48cc-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
