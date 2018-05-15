---
title: Cargar información del esquema de un conjunto de datos desde XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 4b212a7233e6eec93cdce3e521b58e08745e35e0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="4502e-102">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="4502e-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="4502e-103">El esquema de un <xref:System.Data.DataSet> (sus tablas, columnas, relaciones y restricciones) pueden definirse mediante programación, creado por la **rellenar** o **FillSchema** métodos de un <xref:System.Data.Common.DataAdapter>, o la carga desde un Documento XML.</span><span class="sxs-lookup"><span data-stu-id="4502e-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="4502e-104">Para cargar **conjunto de datos** información del esquema de un documento XML, puede usar el **ReadXmlSchema** o la **InferXmlSchema** método de la **delconjuntodedatos**.</span><span class="sxs-lookup"><span data-stu-id="4502e-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="4502e-105">**ReadXmlSchema** le permite cargar o deducir **conjunto de datos** información del esquema del documento que contiene el esquema de lenguaje (XSD) de definición de esquemas de XML o un documento XML con un esquema XML alineado.</span><span class="sxs-lookup"><span data-stu-id="4502e-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="4502e-106">**InferXmlSchema** le permite deducir el esquema del documento XML y pasar por alto ciertos espacios de nombres XML que especifique.</span><span class="sxs-lookup"><span data-stu-id="4502e-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4502e-107">Orden de las tablas una **conjunto de datos** podría no conservarse, cuando usa servicios Web o serialización XML para transferir un **conjunto de datos** que se creó en memoria mediante construcciones XSD (como las relaciones anidadas).</span><span class="sxs-lookup"><span data-stu-id="4502e-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="4502e-108">Por lo tanto, el destinatario de la **conjunto de datos** no debe depender orden de las tablas en este caso.</span><span class="sxs-lookup"><span data-stu-id="4502e-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="4502e-109">Sin embargo, orden de las tablas siempre se mantiene si el esquema de la **conjunto de datos** que se transfieren se leyó desde archivos XSD, en lugar de crearse en memoria.</span><span class="sxs-lookup"><span data-stu-id="4502e-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="4502e-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="4502e-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="4502e-111">Para cargar el esquema de un **conjunto de datos** desde un documento XML sin cargar ningún dato, puede utilizar el **ReadXmlSchema** método de la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="4502e-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="4502e-112">**ReadXmlSchema** crea **conjunto de datos** esquema definido mediante el esquema XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="4502e-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="4502e-113">El **ReadXmlSchema** método toma un único argumento de un nombre de archivo, una secuencia o un **XmlReader** que contiene el documento XML que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="4502e-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="4502e-114">El documento XML puede contener únicamente el esquema o puede contener el esquema alineado con elementos XML que contienen datos.</span><span class="sxs-lookup"><span data-stu-id="4502e-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="4502e-115">Para obtener más información acerca de cómo escribir el esquema en línea como esquema XML, vea [derivar estructura relacional de DataSet de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="4502e-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="4502e-116">Si el documento XML pasado a **ReadXmlSchema** no contiene ninguna información de esquema en línea, **ReadXmlSchema** deducirá el esquema a partir de los elementos en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="4502e-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="4502e-117">Si el **conjunto de datos** ya contiene un esquema, se extenderá el esquema actual mediante la adición de nuevas tablas si aún no existen.</span><span class="sxs-lookup"><span data-stu-id="4502e-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="4502e-118">En las tablas existentes no se agregarán nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="4502e-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="4502e-119">Si una columna que se va a agregar ya existe en el **conjunto de datos** aunque tiene un tipo incompatible con la columna en el código XML, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="4502e-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="4502e-120">Para obtener más información acerca de cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [deducir el conjunto de datos relacional estructura de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4502e-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="4502e-121">Aunque **ReadXmlSchema** carga o deduce únicamente el esquema de un **conjunto de datos**, **ReadXml** método de la **conjunto de datos** carga o deduce ambos el esquema y los datos contenidos en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="4502e-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="4502e-122">Para obtener más información, consulte [cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4502e-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="4502e-123">Los ejemplos de código siguiente muestran cómo cargar un **conjunto de datos** esquema a partir de un documento o secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="4502e-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="4502e-124">El primer ejemplo muestra un nombre de archivo de esquema XML que se pasan a la **ReadXmlSchema** método.</span><span class="sxs-lookup"><span data-stu-id="4502e-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="4502e-125">El segundo ejemplo se muestra un **System.IO.StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="4502e-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="4502e-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="4502e-126">InferXmlSchema</span></span>  
 <span data-ttu-id="4502e-127">También puede indicar la **conjunto de datos** deduzca su esquema a partir de un documento XML utilizando la **InferXmlSchema** método de la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="4502e-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="4502e-128">**InferXmlSchema** funciona del mismo modo que **ReadXml** con una **XmlReadMode** de **InferSchema** (carga los datos, así como deduce el esquema) y **ReadXmlSchema** si el documento que se está leyendo no contiene ningún esquema en línea.</span><span class="sxs-lookup"><span data-stu-id="4502e-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="4502e-129">Sin embargo, **InferXmlSchema** ofrece la posibilidad adicional de permitir para especificar determinados espacios de nombres XML que se omita cuando se deduzca el esquema.</span><span class="sxs-lookup"><span data-stu-id="4502e-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="4502e-130">**InferXmlSchema** toma dos argumentos necesarios: la ubicación del documento XML, especificado por un nombre de archivo, una secuencia o un **XmlReader**; y una matriz de cadenas de espacios de nombres XML que se omitan por la operación.</span><span class="sxs-lookup"><span data-stu-id="4502e-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="4502e-131">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="4502e-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="4502e-132">Debido a los atributos especificados para los elementos en el documento XML anterior, tanto el **ReadXmlSchema** método y **ReadXml** método con un **XmlReadMode** de **InferSchema** crear tablas para cada elemento en el documento: **categorías**, **CategoryID**, **CategoryName**, **Descripción**, **productos**, **ProductID**, **ReorderLevel**, y **no incluye**.</span><span class="sxs-lookup"><span data-stu-id="4502e-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="4502e-133">(Para obtener más información, consulte [deducir el conjunto de datos relacional estructura de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Sin embargo, una estructura más adecuada sería crear únicamente la **categorías** y **productos** tablas y, a continuación, crear **CategoryID**, **CategoryName** , y **descripción** columnas en la **categorías** tabla, y **ProductID**, **ReorderLevel**, y **Discontinued** columnas en la **productos** tabla.</span><span class="sxs-lookup"><span data-stu-id="4502e-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="4502e-134">Para asegurarse de que el esquema inferido pasa por alto los atributos especificados en los elementos XML, use la **InferXmlSchema** método y especifique el espacio de nombres XML **officedata** que se omitan, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4502e-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="4502e-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4502e-135">See Also</span></span>  
 [<span data-ttu-id="4502e-136">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="4502e-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="4502e-137">Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="4502e-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="4502e-138">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="4502e-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="4502e-139">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="4502e-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="4502e-140">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="4502e-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="4502e-141">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="4502e-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
