---
title: XmlSchemaSet para compilación de esquemas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c4b175-3170-4071-9d60-dd5a42f79b54
ms.openlocfilehash: 5916511187741c703cb39a5c168e542e124ab26b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825928"
---
# <a name="xmlschemaset-for-schema-compilation"></a><span data-ttu-id="2ad2b-102">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="2ad2b-102">XmlSchemaSet for Schema Compilation</span></span>
<span data-ttu-id="2ad2b-103">Describe la clase <xref:System.Xml.Schema.XmlSchemaSet>, una caché en la que se pueden almacenar y validar esquemas del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="2ad2b-103">Describes the <xref:System.Xml.Schema.XmlSchemaSet>, a cache where XML Schema definition language (XSD) schemas can be stored and validated.</span></span>  
  
## <a name="the-xmlschemaset-class"></a><span data-ttu-id="2ad2b-104">La clase XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="2ad2b-104">The XmlSchemaSet Class</span></span>  
 <span data-ttu-id="2ad2b-105"><xref:System.Xml.Schema.XmlSchemaSet> es una caché en la que se pueden almacenar y validar esquemas del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="2ad2b-105">The <xref:System.Xml.Schema.XmlSchemaSet> is a cache where XML Schema definition language (XSD) schemas can be stored and validated.</span></span>  
  
 <span data-ttu-id="2ad2b-106">En la versión 1.0 de <xref:System.Xml?displayProperty=nameWithType>, los esquemas se cargaban en una clase <xref:System.Xml.Schema.XmlSchemaCollection> como una biblioteca de esquemas.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-106">In <xref:System.Xml?displayProperty=nameWithType> version 1.0, XML schemas were loaded into an <xref:System.Xml.Schema.XmlSchemaCollection> class as a library of schemas.</span></span> <span data-ttu-id="2ad2b-107">En la versión 2.0 de <xref:System.Xml?displayProperty=nameWithType>, las clases <xref:System.Xml.XmlValidatingReader> y <xref:System.Xml.Schema.XmlSchemaCollection> están obsoletas y se han reemplazado por los métodos <xref:System.Xml.XmlReader.Create%2A> y la clase <xref:System.Xml.Schema.XmlSchemaSet>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-107">In <xref:System.Xml?displayProperty=nameWithType> version 2.0, the <xref:System.Xml.XmlValidatingReader> and the <xref:System.Xml.Schema.XmlSchemaCollection> classes are obsolete, and have been replaced by the <xref:System.Xml.XmlReader.Create%2A> methods, and the <xref:System.Xml.Schema.XmlSchemaSet> class respectively.</span></span>  
  
 <span data-ttu-id="2ad2b-108"><xref:System.Xml.Schema.XmlSchemaSet> se introdujo para solucionar una serie de problemas, entre los que se incluyen la compatibilidad con estándares, el rendimiento y el formato obsoleto de esquemas reducidos de datos XML (XDR) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-108">The <xref:System.Xml.Schema.XmlSchemaSet> has been introduced to fix a number of issues including standards compatibility, performance, and the obsolete Microsoft XML-Data Reduced (XDR) schema format.</span></span>  
  
 <span data-ttu-id="2ad2b-109">A continuación se ofrece una comparación entre la clase <xref:System.Xml.Schema.XmlSchemaCollection> y la clase <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-109">The following is a comparison between the <xref:System.Xml.Schema.XmlSchemaCollection> class and the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span>  
  
|<span data-ttu-id="2ad2b-110">XmlSchemaCollection</span><span class="sxs-lookup"><span data-stu-id="2ad2b-110">XmlSchemaCollection</span></span>|<span data-ttu-id="2ad2b-111">XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="2ad2b-111">XmlSchemaSet</span></span>|  
|-------------------------|------------------|  
|<span data-ttu-id="2ad2b-112">Es compatible con los esquemas XML del W3C y del XDR de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-112">Supports Microsoft XDR and W3C XML schemas.</span></span>|<span data-ttu-id="2ad2b-113">Solo es compatible con los esquemas XML del W3C.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-113">Only supports W3C XML schemas.</span></span>|  
|<span data-ttu-id="2ad2b-114">Los esquemas se compilan cuando se llama al método <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-114">Schemas are compiled when the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method is called.</span></span>|<span data-ttu-id="2ad2b-115">Los esquemas no se compilan cuando se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-115">Schemas are not compiled when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method is called.</span></span> <span data-ttu-id="2ad2b-116">Esto proporciona una mejora del rendimiento durante la creación de la biblioteca de esquemas.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-116">This provides a performance improvement during creation of the schema library.</span></span>|  
|<span data-ttu-id="2ad2b-117">Cada esquema genera una versión compilada individual que puede generar "islas de esquemas".</span><span class="sxs-lookup"><span data-stu-id="2ad2b-117">Each schema generates an individual compiled version that can result in "schema islands."</span></span> <span data-ttu-id="2ad2b-118">Como resultado, todas las inclusiones e importaciones solo tienen el ámbito de ese esquema.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-118">As a result, all includes and imports are scoped only within that schema.</span></span>|<span data-ttu-id="2ad2b-119">Los esquemas compilados generan un esquema único lógico, es decir, un "conjunto" de esquemas.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-119">Compiled schemas generate a single logical schema, a "set" of schemas.</span></span> <span data-ttu-id="2ad2b-120">Cualquier esquema importado a un esquema que se haya agregado al conjunto, también se agrega directamente al conjunto.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-120">Any imported schemas within a schema that are added to the set are directly added to the set themselves.</span></span> <span data-ttu-id="2ad2b-121">Esto significa que todos los tipos están disponibles para todos los esquemas.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-121">This means that all types are available to all schemas.</span></span>|  
|<span data-ttu-id="2ad2b-122">Solo puede haber en la colección un esquema para un espacio de nombres de destino concreto.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-122">Only one schema for a particular target namespace can exist in the collection.</span></span>|<span data-ttu-id="2ad2b-123">Se pueden agregar varios esquemas para el mismo espacio de nombres de destino siempre y cuando no haya conflictos de tipo.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-123">Multiple schemas for the same target namespace can be added as long as there are no type conflicts.</span></span>|  
  
## <a name="migrating-to-the-xmlschemaset"></a><span data-ttu-id="2ad2b-124">Migración a XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="2ad2b-124">Migrating to the XmlSchemaSet</span></span>  
 <span data-ttu-id="2ad2b-125">En el siguiente código muestra se proporciona una guía para realizar la migración a la nueva clase <xref:System.Xml.Schema.XmlSchemaSet> desde la clase <xref:System.Xml.Schema.XmlSchemaCollection> obsoleta.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-125">The following code example provides a guide to migrating to the new <xref:System.Xml.Schema.XmlSchemaSet> class from the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> class.</span></span> <span data-ttu-id="2ad2b-126">El código muestra ilustra las siguientes diferencias principales entre las dos clases.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-126">The code example illustrates the following major differences between the two classes.</span></span>  
  
- <span data-ttu-id="2ad2b-127">Al contrario que el método <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> de la clase <xref:System.Xml.Schema.XmlSchemaCollection>, los esquemas no se compilan al llamar al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-127">Unlike the <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaCollection> class, schemas are not compiled when calling the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-128">El método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de <xref:System.Xml.Schema.XmlSchemaSet> se llama explícitamente en el código muestra.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-128">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is explicitly called in the example code.</span></span>  
  
- <span data-ttu-id="2ad2b-129">Para iterar sobre <xref:System.Xml.Schema.XmlSchemaSet>, se debe utilizar la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-129">To iterate over an <xref:System.Xml.Schema.XmlSchemaSet>, you must use the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="2ad2b-130">Éste es el código muestra de <xref:System.Xml.Schema.XmlSchemaCollection> obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-130">The following is the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> code example.</span></span>  
  
```vb  
Dim schemaCollection As XmlSchemaCollection = New XmlSchemaCollection()  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema in schemaCollection  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaCollection schemaCollection = new XmlSchemaCollection();  
schemaCollection.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaCollection.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
  
foreach(XmlSchema schema in schemaCollection)  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
 <span data-ttu-id="2ad2b-131">Éste es el código muestra de <xref:System.Xml.Schema.XmlSchemaSet> equivalente.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-131">The following is the equivalent <xref:System.Xml.Schema.XmlSchemaSet> code example.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim schema As XmlSchema  
  
For Each schema in schemaSet.Schemas()  
  
   Console.WriteLine(schema.TargetNamespace)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
foreach(XmlSchema schema in schemaSet.Schemas())  
{  
   Console.WriteLine(schema.TargetNamespace);  
}  
```  
  
## <a name="adding-and-retrieving-schemas"></a><span data-ttu-id="2ad2b-132">Adición y recuperación de esquemas</span><span class="sxs-lookup"><span data-stu-id="2ad2b-132">Adding and Retrieving Schemas</span></span>  
 <span data-ttu-id="2ad2b-133">Los esquemas se agregan a <xref:System.Xml.Schema.XmlSchemaSet> con el método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-133">Schemas are added to an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-134">Cuando se agrega un esquema a <xref:System.Xml.Schema.XmlSchemaSet>, se asocia a un identificador URI de espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-134">When a schema is added to an <xref:System.Xml.Schema.XmlSchemaSet>, it is associated with a target namespace URI.</span></span> <span data-ttu-id="2ad2b-135">El identificador URI de espacio de nombres de destino se puede especificar como parámetro para el método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> o, si no se especifica ningún espacio de nombres de destino, <xref:System.Xml.Schema.XmlSchemaSet> utiliza el espacio de nombres de destino que se ha definido en el esquema.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-135">The target namespace URI can either be specified as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method or if no target namespace is specified, the <xref:System.Xml.Schema.XmlSchemaSet> uses the target namespace defined in the schema.</span></span>  
  
 <span data-ttu-id="2ad2b-136">Los esquemas se recuperan de <xref:System.Xml.Schema.XmlSchemaSet> con la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-136">Schemas are retrieved from an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-137">La propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> de <xref:System.Xml.Schema.XmlSchemaSet> permite iterar sobre los objetos <xref:System.Xml.Schema.XmlSchema> contenidos en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-137">The <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> allows you to iterate over the <xref:System.Xml.Schema.XmlSchema> objects contained in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-138">La propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> devuelve todos los objetos <xref:System.Xml.Schema.XmlSchema> contenidos en <xref:System.Xml.Schema.XmlSchemaSet> o, dado un parámetro de espacio de nombres de destino, devuelve todos los objetos <xref:System.Xml.Schema.XmlSchema> que pertenecen al espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-138">The <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property either returns all the <xref:System.Xml.Schema.XmlSchema> objects contained in the <xref:System.Xml.Schema.XmlSchemaSet>, or, given a target namespace parameter, returns all the <xref:System.Xml.Schema.XmlSchema> objects that belong to the target namespace.</span></span> <span data-ttu-id="2ad2b-139">Si se especifica `null` como el parámetro del espacio de nombres de destino, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> devuelve todos los esquemas sin un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-139">If `null` is specified as the target namespace parameter, the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property returns all schemas without a namespace.</span></span>  
  
 <span data-ttu-id="2ad2b-140">En el siguiente ejemplo se agrega el esquema `books.xsd` del espacio de nombres `http://www.contoso.com/books` a <xref:System.Xml.Schema.XmlSchemaSet>, se recuperan todos los esquemas que pertenecen al espacio de nombres `http://www.contoso.com/books` del <xref:System.Xml.Schema.XmlSchemaSet> y, a continuación, se escriben dichos esquemas en <xref:System.Console>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-140">The following example adds the `books.xsd` schema in the `http://www.contoso.com/books` namespace to an <xref:System.Xml.Schema.XmlSchemaSet>, retrieves all schemas that belong to the `http://www.contoso.com/books` namespace from the <xref:System.Xml.Schema.XmlSchemaSet>, and then writes those schemas to the <xref:System.Console>.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas("http://www.contoso.com/books")  
  
   schema.Write(Console.Out)  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas("http://www.contoso.com/books"))  
{  
   schema.Write(Console.Out);  
}  
```  
  
 <span data-ttu-id="2ad2b-141">Para obtener más información sobre cómo agregar y recuperar esquemas de un objeto <xref:System.Xml.Schema.XmlSchemaSet>, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> y la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A></span><span class="sxs-lookup"><span data-stu-id="2ad2b-141">For more information about adding and retrieving schemas from an <xref:System.Xml.Schema.XmlSchemaSet> object, see the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method and the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property reference documentation.</span></span>  
  
## <a name="compiling-schemas"></a><span data-ttu-id="2ad2b-142">Compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="2ad2b-142">Compiling Schemas</span></span>  
 <span data-ttu-id="2ad2b-143">Los esquemas de <xref:System.Xml.Schema.XmlSchemaSet> se compilan en un solo esquema lógico por medio del método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-143">Schemas in an <xref:System.Xml.Schema.XmlSchemaSet> are compiled into one logical schema by the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ad2b-144">A diferencia de la clase <xref:System.Xml.Schema.XmlSchemaCollection> obsoleta, los esquemas no se compilan cuando se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-144">Unlike the obsolete <xref:System.Xml.Schema.XmlSchemaCollection> class, schemas are not compiled when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method is called.</span></span>  
  
 <span data-ttu-id="2ad2b-145">Si el método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> se ejecuta correctamente, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> de <xref:System.Xml.Schema.XmlSchemaSet> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-145">If the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method executes successfully, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> is set to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ad2b-146">La propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> no resulta afectada si se editan los esquemas mientras está en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-146">The <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property is not affected if schemas are edited while in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-147">No se realiza un seguimiento de las actualizaciones de los esquemas individuales en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-147">Updates of the individual schemas in the <xref:System.Xml.Schema.XmlSchemaSet> are not tracked.</span></span> <span data-ttu-id="2ad2b-148">Como resultado, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> puede ser `true` aunque se haya modificado uno de los esquemas contenidos en <xref:System.Xml.Schema.XmlSchemaSet>, siempre y cuando no se hayan agregado ni quitado esquemas de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-148">As a result, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property can be `true` even though one of the schemas contained in the <xref:System.Xml.Schema.XmlSchemaSet> has been altered, as long as no schemas were added or removed from the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="2ad2b-149">En el siguiente ejemplo, se agrega el archivo `books.xsd` a <xref:System.Xml.Schema.XmlSchemaSet> y, a continuación, se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-149">The following example adds the `books.xsd` file to the <xref:System.Xml.Schema.XmlSchemaSet> and then calls the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/books", "books.xsd")  
schemaSet.Compile()  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/books", "books.xsd");  
schemaSet.Compile();  
```  
  
 <span data-ttu-id="2ad2b-150">Para obtener más información sobre la compilación de esquemas en <xref:System.Xml.Schema.XmlSchemaSet>, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-150">For more information about compiling schemas in an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method reference documentation.</span></span>  
  
## <a name="reprocessing-schemas"></a><span data-ttu-id="2ad2b-151">Reprocesamiento de esquemas</span><span class="sxs-lookup"><span data-stu-id="2ad2b-151">Reprocessing Schemas</span></span>  
 <span data-ttu-id="2ad2b-152">El reprocesamiento de un esquema en <xref:System.Xml.Schema.XmlSchemaSet> realiza todos los pasos previos al procesamiento que se deben realizar en un esquema cuando se llama al método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-152">Reprocessing a schema in an <xref:System.Xml.Schema.XmlSchemaSet> performs all the preprocessing steps performed on a schema when the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called.</span></span> <span data-ttu-id="2ad2b-153">Si la llamada al método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> es correcta, la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> de <xref:System.Xml.Schema.XmlSchemaSet> se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-153">If the call to the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method is successful, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> is set to `false`.</span></span>  
  
 <span data-ttu-id="2ad2b-154">El método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> se debería utilizar cuando se haya modificado un esquema de <xref:System.Xml.Schema.XmlSchemaSet> después de que <xref:System.Xml.Schema.XmlSchemaSet> haya realizado la compilación.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-154">The <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method should be used when a schema in the <xref:System.Xml.Schema.XmlSchemaSet> has been modified after the <xref:System.Xml.Schema.XmlSchemaSet> has performed compilation.</span></span>  
  
 <span data-ttu-id="2ad2b-155">En el siguiente ejemplo se ilustra el reprocesamiento de un esquema agregado a <xref:System.Xml.Schema.XmlSchemaSet> utilizando el método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-155">The following example illustrates reprocessing a schema added to the <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method.</span></span> <span data-ttu-id="2ad2b-156">Después de compilar <xref:System.Xml.Schema.XmlSchemaSet> con el método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> y después de modificar el esquema agregado a <xref:System.Xml.Schema.XmlSchemaSet>, se establece la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> en `true` aunque se haya modificado un esquema en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-156">After the <xref:System.Xml.Schema.XmlSchemaSet> is compiled using the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method, and the schema added to the <xref:System.Xml.Schema.XmlSchemaSet> is modified, the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property is set to `true` even though a schema in the <xref:System.Xml.Schema.XmlSchemaSet> has been modified.</span></span> <span data-ttu-id="2ad2b-157">Al llamar al método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>, se realiza todo el procesamiento previo mediante el método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> y la propiedad <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-157">Calling the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method performs all the preprocessing performed by the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method, and sets the <xref:System.Xml.Schema.XmlSchemaSet.IsCompiled%2A> property to `false`.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
Dim schema As XmlSchema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Compile()  
  
Dim element As XmlSchemaElement = New XmlSchemaElement()  
schema.Items.Add(element)  
element.Name = "book"  
element.SchemaTypeName = New XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema")  
  
schemaSet.Reprocess(schema)  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
XmlSchema schema = schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Compile();  
  
XmlSchemaElement element = new XmlSchemaElement();  
schema.Items.Add(element);  
element.Name = "book";  
element.SchemaTypeName = new XmlQualifiedName("string", "http://www.w3.org/2001/XMLSchema");  
  
schemaSet.Reprocess(schema);  
```  
  
 <span data-ttu-id="2ad2b-158">Para obtener más información sobre el reprocesamiento de un esquema en <xref:System.Xml.Schema.XmlSchemaSet>, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-158">For more information about reprocessing a schema in an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> method reference documentation.</span></span>  
  
## <a name="checking-for-a-schema"></a><span data-ttu-id="2ad2b-159">Comprobación de un esquema</span><span class="sxs-lookup"><span data-stu-id="2ad2b-159">Checking for a Schema</span></span>  
 <span data-ttu-id="2ad2b-160">Puede utilizar el método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> de <xref:System.Xml.Schema.XmlSchemaSet> para comprobar si hay contenido un esquema en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-160">You can use the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> to check if a schema is contained within an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-161">El método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> toma un espacio de nombres de destino o un objeto <xref:System.Xml.Schema.XmlSchema> para comprobarlos.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-161">The <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method takes either a target namespace or an <xref:System.Xml.Schema.XmlSchema> object to check for.</span></span> <span data-ttu-id="2ad2b-162">En cualquiera de los casos, el método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> devuelve `true` si el esquema está contenido en <xref:System.Xml.Schema.XmlSchemaSet>; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-162">In either case, the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method returns `true` if the schema is contained within the <xref:System.Xml.Schema.XmlSchemaSet>; otherwise, it returns `false`.</span></span>  
  
 <span data-ttu-id="2ad2b-163">Para obtener más información sobre la comprobación de un esquema, vea la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-163">For more information about checking for a schema, see the <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A> method reference documentation.</span></span>  
  
## <a name="removing-schemas"></a><span data-ttu-id="2ad2b-164">Cómo quitar esquemas</span><span class="sxs-lookup"><span data-stu-id="2ad2b-164">Removing Schemas</span></span>  
 <span data-ttu-id="2ad2b-165">Los esquemas se quitan de un <xref:System.Xml.Schema.XmlSchemaSet> utilizando los métodos <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> y <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-165">Schemas are removed from an <xref:System.Xml.Schema.XmlSchemaSet> using the <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> and <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-166">El método <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> elimina el esquema especificado de <xref:System.Xml.Schema.XmlSchemaSet>, mientras el método <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> quita el esquema especificado y el resto de los esquemas que importa desde <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-166">The <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> method removes the specified schema from the <xref:System.Xml.Schema.XmlSchemaSet>, while the <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> method removes the specified schema and all the schemas it imports from the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="2ad2b-167">El siguiente ejemplo ilustra cómo agregar varios esquemas a <xref:System.Xml.Schema.XmlSchemaSet> y, a continuación, cómo utilizar el método <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> para quitar uno de los esquemas y todos los esquemas que importa.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-167">The following example illustrates adding multiple schemas to an <xref:System.Xml.Schema.XmlSchemaSet>, then using the <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> method to remove one of the schemas and all the schemas it imports.</span></span>  
  
```vb  
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd")  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd")  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd")  
  
Dim schema As XmlSchema  
  
For Each schema In schemaSet.Schemas()  
  
   If schema.TargetNamespace = "http://www.contoso.com/music" Then  
      schemaSet.RemoveRecursive(schema)  
   End If  
  
Next  
```  
  
```csharp  
XmlSchemaSet schemaSet = new XmlSchemaSet();  
schemaSet.Add("http://www.contoso.com/retail", "http://www.contoso.com/retail.xsd");  
schemaSet.Add("http://www.contoso.com/books", "http://www.contoso.com/books.xsd");  
schemaSet.Add("http://www.contoso.com/music", "http://www.contoso.com/music.xsd");  
  
foreach (XmlSchema schema in schemaSet.Schemas())  
{  
   if (schema.TargetNamespace == "http://www.contoso.com/music")  
   {  
      schemaSet.RemoveRecursive(schema);  
   }  
}  
```  
  
 <span data-ttu-id="2ad2b-168">Para obtener más información sobre cómo quitar esquemas de <xref:System.Xml.Schema.XmlSchemaSet>, vea <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> y la documentación de referencia del método <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-168">For more information about removing schemas from an <xref:System.Xml.Schema.XmlSchemaSet>, see the <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A> and <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A> methods reference documentation.</span></span>  
  
## <a name="schema-resolution-and-xsimport"></a><span data-ttu-id="2ad2b-169">Resolución de esquemas y xs:import</span><span class="sxs-lookup"><span data-stu-id="2ad2b-169">Schema Resolution and xs:import</span></span>  
 <span data-ttu-id="2ad2b-170">En los siguientes ejemplos se describe el comportamiento de <xref:System.Xml.Schema.XmlSchemaSet> para importar esquemas cuando existen varios esquemas para un espacio de nombres determinado en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-170">The following examples describe the <xref:System.Xml.Schema.XmlSchemaSet> behavior for importing schemas when multiple schemas for a given namespace exist in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
 <span data-ttu-id="2ad2b-171">Por ejemplo, piense en un <xref:System.Xml.Schema.XmlSchemaSet> que contiene múltiples esquemas para el espacio de nombres `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-171">For example, consider an <xref:System.Xml.Schema.XmlSchemaSet> that contains multiple schemas for the `http://www.contoso.com` namespace.</span></span> <span data-ttu-id="2ad2b-172">Se agrega un esquema con la directiva `xs:import` siguiente a <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-172">A schema with the following `xs:import` directive is added to the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
```xml  
<xs:import namespace="http://www.contoso.com" schemaLocation="http://www.contoso.com/schema.xsd" />  
```  
  
 <span data-ttu-id="2ad2b-173"><xref:System.Xml.Schema.XmlSchemaSet> intenta importar un esquema para el espacio de nombres `http://www.contoso.com` cargándolo desde la URL `http://www.contoso.com/schema.xsd`.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-173">The <xref:System.Xml.Schema.XmlSchemaSet> attempts to import a schema for the `http://www.contoso.com` namespace by loading it from the `http://www.contoso.com/schema.xsd` URL.</span></span> <span data-ttu-id="2ad2b-174">En el esquema de importación solo están disponibles los tipos y la declaración de esquema que se declaran en el documento de esquema, aunque hay otros documentos de esquema para el espacio de nombres `http://www.contoso.com` en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-174">Only the schema declaration and types declared in the schema document are available in the importing schema, even though there are other schema documents for the `http://www.contoso.com` namespace in the <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-175">Si no se puede encontrar el archivo `schema.xsd` en la URL `http://www.contoso.com/schema.xsd`, no se importa ningún esquema para el espacio de nombres `http://www.contoso.com` al esquema de importación.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-175">If the `schema.xsd` file cannot be located at the `http://www.contoso.com/schema.xsd` URL, no schema for the `http://www.contoso.com` namespace is imported into the importing schema.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="2ad2b-176">Validación de documentos XML</span><span class="sxs-lookup"><span data-stu-id="2ad2b-176">Validating XML Documents</span></span>  
 <span data-ttu-id="2ad2b-177">Los documentos XML se pueden validar con esquemas en <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-177">XML documents can be validated against schemas in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="2ad2b-178">Para validar un documento XML, agregue un esquema a la propiedad <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> de un objeto <xref:System.Xml.XmlReaderSettings> o agregue <xref:System.Xml.Schema.XmlSchemaSet> a la propiedad <xref:System.Xml.XmlReaderSettings.Schemas%2A> de un objeto <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-178">You validate an XML document by adding a schema to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of an <xref:System.Xml.XmlReaderSettings> object, or by adding an <xref:System.Xml.Schema.XmlSchemaSet> to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of an <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="2ad2b-179">A continuación, el método <xref:System.Xml.XmlReaderSettings> de la clase <xref:System.Xml.XmlReader.Create%2A> utiliza el objeto <xref:System.Xml.XmlReader> para crear un objeto <xref:System.Xml.XmlReader> y validar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="2ad2b-179">The <xref:System.Xml.XmlReaderSettings> object is then used by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class to create an <xref:System.Xml.XmlReader> object and validate the XML document.</span></span>  
  
 <span data-ttu-id="2ad2b-180">Para más información sobre la validación de documentos XML con una clase <xref:System.Xml.Schema.XmlSchemaSet>, vea [Validación de esquema XML (XSD) con XmlSchemaSet](xml-schema-xsd-validation-with-xmlschemaset.md).</span><span class="sxs-lookup"><span data-stu-id="2ad2b-180">For more information about validating XML documents using an <xref:System.Xml.Schema.XmlSchemaSet>, see [XML Schema (XSD) Validation with XmlSchemaSet](xml-schema-xsd-validation-with-xmlschemaset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad2b-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ad2b-181">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Contains%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.Remove%2A>
- <xref:System.Xml.Schema.XmlSchemaSet.RemoveRecursive%2A>
- [<span data-ttu-id="2ad2b-182">XmlSchemaSet como una memoria caché de esquema</span><span class="sxs-lookup"><span data-stu-id="2ad2b-182">XmlSchemaSet as a Schema Cache</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="2ad2b-183">Validación de esquema XML (XSD) con XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="2ad2b-183">XML Schema (XSD) Validation with XmlSchemaSet</span></span>](xml-schema-xsd-validation-with-xmlschemaset.md)
