---
title: Cargar información del esquema de un conjunto de datos desde XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151057"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="95400-102">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="95400-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="95400-103">El esquema <xref:System.Data.DataSet> de un (sus tablas, columnas, relaciones y restricciones) se puede definir <xref:System.Data.Common.DataAdapter>mediante programación, creado por el **Fill** o **FillSchema** métodos de un , o cargado desde un documento XML.</span><span class="sxs-lookup"><span data-stu-id="95400-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="95400-104">Para cargar información de esquema **DataSet** desde un documento XML, puede utilizar el método **ReadXmlSchema** o **InferXmlSchema** del **dataSet**.</span><span class="sxs-lookup"><span data-stu-id="95400-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="95400-105">**ReadXmlSchema** permite cargar o inferir información de esquema **DataSet** del documento que contiene el esquema del lenguaje de definición de esquemas XML (XSD) o un documento XML con esquema XML en línea.</span><span class="sxs-lookup"><span data-stu-id="95400-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="95400-106">**InferXmlSchema** permite deducir el esquema del documento XML mientras se ignoran determinados espacios de nombres XML que especifique.</span><span class="sxs-lookup"><span data-stu-id="95400-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95400-107">Es posible que el orden de tablas en un **dataSet** no se conserve cuando se usan servicios web o serialización XML para transferir un **dataset** que se creó en memoria mediante construcciones XSD (como relaciones anidadas).</span><span class="sxs-lookup"><span data-stu-id="95400-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="95400-108">Por lo tanto, el destinatario del **dataSet** no debe depender del orden de la tabla en este caso.</span><span class="sxs-lookup"><span data-stu-id="95400-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="95400-109">Sin embargo, el orden de tablas siempre se conserva si el esquema del **conjunto** de datos que se transfiere se leyó desde archivos XSD, en lugar de crearse en memoria.</span><span class="sxs-lookup"><span data-stu-id="95400-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="95400-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="95400-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="95400-111">Para cargar el esquema de un **DataSet** desde un documento XML sin cargar ningún dato, puede utilizar el método **ReadXmlSchema** del **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="95400-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="95400-112">**ReadXmlSchema** crea el esquema **DataSet** definido mediante el esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="95400-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="95400-113">El **ReadXmlSchema** método toma un único argumento de un nombre de archivo, una secuencia o un **XmlReader** que contiene el documento XML que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="95400-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="95400-114">El documento XML puede contener únicamente el esquema o puede contener el esquema alineado con elementos XML que contienen datos.</span><span class="sxs-lookup"><span data-stu-id="95400-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="95400-115">Para obtener más información sobre cómo escribir el esquema en línea como esquema XML, vea Derivar la estructura relacional del conjunto de datos desde el [esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="95400-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="95400-116">Si el documento XML pasado a **ReadXmlSchema** no contiene información de esquema en línea, **ReadXmlSchema** deducirá el esquema de los elementos del documento XML.</span><span class="sxs-lookup"><span data-stu-id="95400-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="95400-117">Si el **DataSet** ya contiene un esquema, el esquema actual se ampliará agregando nuevas tablas si aún no existen.</span><span class="sxs-lookup"><span data-stu-id="95400-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="95400-118">En las tablas existentes no se agregarán nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="95400-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="95400-119">Si una columna que se agrega ya existe en el **conjunto** de datos pero tiene un tipo incompatible con la columna que se encuentra en el XML, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="95400-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="95400-120">Para obtener más información sobre cómo **ReadXmlSchema** deduce un esquema de un documento XML, vea [Inferir](inferring-dataset-relational-structure-from-xml.md)estructura relacional de conjunto de datos de XML .</span><span class="sxs-lookup"><span data-stu-id="95400-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="95400-121">Aunque **ReadXmlSchema** carga o deduce solo el esquema de un **DataSet**, el **ReadXml** método de la **DataSet** carga o deduce tanto el esquema y los datos contenidos en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="95400-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="95400-122">Para obtener más información, consulte [Carga de un conjunto](loading-a-dataset-from-xml.md)de datos desde XML .</span><span class="sxs-lookup"><span data-stu-id="95400-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="95400-123">En los ejemplos de código siguientes se muestra cómo cargar un esquema **DataSet** desde un documento o secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="95400-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="95400-124">En el primer ejemplo se muestra un nombre de archivo de esquema XML que se pasa a la **ReadXmlSchema** método.</span><span class="sxs-lookup"><span data-stu-id="95400-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="95400-125">En el segundo ejemplo se muestra un **archivo System.IO.StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="95400-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="95400-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="95400-126">InferXmlSchema</span></span>  
 <span data-ttu-id="95400-127">También puede indicar al **DataSet** que deduzca su esquema de un documento XML mediante el método **InferXmlSchema** del **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="95400-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="95400-128">**InferXmlSchema** funciona igual que **ReadXml** con un **XmlReadMode** de **InferSchema** (carga datos, así como deduce el esquema) y **ReadXmlSchema** si el documento que se lee no contiene ningún esquema en línea.</span><span class="sxs-lookup"><span data-stu-id="95400-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="95400-129">Sin embargo, **InferXmlSchema** proporciona la capacidad adicional de permitirle especificar espacios de nombres XML concretos que se omitirán cuando se infiere el esquema.</span><span class="sxs-lookup"><span data-stu-id="95400-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="95400-130">**InferXmlSchema** toma dos argumentos necesarios: la ubicación del documento XML, especificada por un nombre de archivo, una secuencia o un **XmlReader**; y una matriz de cadenas de espacios de nombres XML que la operación omitirá.</span><span class="sxs-lookup"><span data-stu-id="95400-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="95400-131">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="95400-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="95400-132">Debido a los atributos especificados para los elementos del documento XML anterior, tanto el método **ReadXmlSchema** como el método **ReadXml** con un **XmlReadMode** de **InferSchema** crearían tablas para cada elemento del documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**y **Discontinued**.</span><span class="sxs-lookup"><span data-stu-id="95400-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="95400-133">(Para obtener más información, consulte [Inferir](inferring-dataset-relational-structure-from-xml.md)estructura relacional de conjunto de datos desde XML .) Sin embargo, una estructura más adecuada sería crear solo las **tablas Categories** y **Products** y, a continuación, crear las columnas **CategoryID**, **CategoryName**y **Description** en las columnas **Categories** y **ProductID**, **ReorderLevel**y **Discontinued** en la tabla **Products.**</span><span class="sxs-lookup"><span data-stu-id="95400-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="95400-134">Para asegurarse de que el esquema deducido omite los atributos especificados en los elementos XML, utilice el método **InferXmlSchema** y especifique el espacio de nombres XML para **officedata** que se omitirá, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="95400-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="95400-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95400-135">See also</span></span>

- [<span data-ttu-id="95400-136">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="95400-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="95400-137">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="95400-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="95400-138">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="95400-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="95400-139">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="95400-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="95400-140">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="95400-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="95400-141">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95400-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
