---
title: Acceso a datos XML fuertemente tipados utilizando XPathNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 898e0f52-8a7c-4d1f-afcd-6ffb28b050b4
ms.openlocfilehash: 7051aeb8cdc25518f99fe093045e7e769ae7f6f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725422"
---
# <a name="accessing-strongly-typed-xml-data-using-xpathnavigator"></a><span data-ttu-id="42b7d-102">Acceso a datos XML fuertemente tipados utilizando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="42b7d-102">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>

<span data-ttu-id="42b7d-103">Como instancia del modelo de datos XPath 2.0, la clase <xref:System.Xml.XPath.XPathNavigator> puede contener datos fuertemente tipados que se asignen a tipos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="42b7d-103">As an instance of the XPath 2.0 data model, the <xref:System.Xml.XPath.XPathNavigator> class can contain strongly typed data that maps to common language runtime (CLR) types.</span></span> <span data-ttu-id="42b7d-104">De acuerdo con el modelo de datos XPath 2.0, solo los elementos y los atributos pueden contener datos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="42b7d-104">According to the XPath 2.0 data model, only elements and attributes can contain strongly typed data.</span></span> <span data-ttu-id="42b7d-105">La clase <xref:System.Xml.XPath.XPathNavigator> proporciona mecanismos para acceder a los datos en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> como datos fuertemente tipados, así como mecanismos para convertir un tipo de datos en otro.</span><span class="sxs-lookup"><span data-stu-id="42b7d-105">The <xref:System.Xml.XPath.XPathNavigator> class provides mechanisms for accessing data within an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object as strongly typed data as well as mechanisms for converting from one data type to another.</span></span>  
  
## <a name="type-information-exposed-by-xpathnavigator"></a><span data-ttu-id="42b7d-106">Información de tipo proporcionada por XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="42b7d-106">Type Information Exposed by XPathNavigator</span></span>  

 <span data-ttu-id="42b7d-107">Técnicamente, los datos de XML 1.0 no tienen tipo, a menos que se procesen con una DTD, un esquema del lenguaje de definición de esquemas XML (XSD) u otro mecanismo.</span><span class="sxs-lookup"><span data-stu-id="42b7d-107">XML 1.0 data is technically without type, unless processed with a DTD, XML schema definition language (XSD) schema, or other mechanism.</span></span> <span data-ttu-id="42b7d-108">Existe una serie de categorías de información de tipo que se pueden asociar a un atributo o elemento XML.</span><span class="sxs-lookup"><span data-stu-id="42b7d-108">There are a number of categories of type information that can be associated with an XML element or attribute.</span></span>  
  
- <span data-ttu-id="42b7d-109">Tipos CLR simples: ninguno de los lenguajes de esquema XML es compatible directamente con los tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="42b7d-109">Simple CLR Types: None of the XML Schema languages support Common Language Runtime (CLR) types directly.</span></span> <span data-ttu-id="42b7d-110">Puesto que es útil poder ver el contenido simple de atributos y elementos como el tipo CLR más apropiado, todo el contenido simple puede tener información del tipo <xref:System.String> en ausencia de información de esquema con cualquier información de esquema agregada que potencialmente refine este contenido con un tipo más apropiado.</span><span class="sxs-lookup"><span data-stu-id="42b7d-110">Because it is useful to be able to view simple element and attribute content as the most appropriate CLR type, all simple content can be typed as <xref:System.String> in the absence of schema information with any added schema information potentially refining this content to a more appropriate type.</span></span> <span data-ttu-id="42b7d-111">Para encontrar el mejor tipo CLR coincidente del contenido simple de atributos y elementos, utilice la propiedad <xref:System.Xml.XPath.XPathNavigator.ValueType%2A>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-111">You can find the best matching CLR type of simple element and attribute content by using the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property.</span></span> <span data-ttu-id="42b7d-112">Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="42b7d-112">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
- <span data-ttu-id="42b7d-113">Listas de tipos simples (CLR): un elemento o atributo con contenido simple puede incluir una lista de valores separados por un espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="42b7d-113">Lists of Simple (CLR) Types: An element or attribute with simple content can contain a list of values separated by white space.</span></span> <span data-ttu-id="42b7d-114">Un esquema XML especifica los valores para que sean un "tipo de lista".</span><span class="sxs-lookup"><span data-stu-id="42b7d-114">The values are specified by an XML Schema to be a "list type."</span></span> <span data-ttu-id="42b7d-115">En ausencia de un esquema XML, ese contenido simple se trataría como un solo nodo de texto.</span><span class="sxs-lookup"><span data-stu-id="42b7d-115">In the absence of an XML Schema, such simple content would be treated as a single text node.</span></span> <span data-ttu-id="42b7d-116">Cuando hay disponible un esquema XML, este contenido simple se puede proporcionar como una serie de valores atómicos, cada uno de los cuales tiene un tipo simple que se asigna a una colección de objetos CLR.</span><span class="sxs-lookup"><span data-stu-id="42b7d-116">When an XML Schema is available, this simple content can be exposed as a series of atomic values each having a simple type that maps to a collection of CLR objects.</span></span> <span data-ttu-id="42b7d-117">Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="42b7d-117">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
- <span data-ttu-id="42b7d-118">Valor con información de tipos: un atributo o elemento validado en el esquema con un tipo simple tiene un valor con información de tipos.</span><span class="sxs-lookup"><span data-stu-id="42b7d-118">Typed Value: A schema-validated attribute or element with a simple type has a typed value.</span></span> <span data-ttu-id="42b7d-119">Este valor es un tipo primitivo, como un tipo numérico, de cadena o fecha.</span><span class="sxs-lookup"><span data-stu-id="42b7d-119">This value is a primitive type such as a numeric, string, or date type.</span></span> <span data-ttu-id="42b7d-120">Todos los tipos simples integrados en XSD se pueden asignar a tipos CLR que proporcionan acceso al valor de un nodo como tipo más apropiado, en lugar de simplemente como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-120">All the built-in simple types in XSD can be mapped to CLR types that provide access to the value of a node as a more appropriate type instead of just as a <xref:System.String>.</span></span> <span data-ttu-id="42b7d-121">Se considera que un elemento con atributos o elementos secundarios es un tipo complejo.</span><span class="sxs-lookup"><span data-stu-id="42b7d-121">An element with attributes or element children is considered to be a complex type.</span></span> <span data-ttu-id="42b7d-122">El valor con información de tipos de un tipo complejo con contenido simple (solo nodos de texto como nodos secundarios) es el mismo que del tipo simple de su contenido.</span><span class="sxs-lookup"><span data-stu-id="42b7d-122">The typed value of a complex type with simple content (only text nodes as children) is the same as that of the simple type of its content.</span></span> <span data-ttu-id="42b7d-123">El valor con información tipos de un tipo complejo con contenido complejo (uno o varios elementos secundarios) es el valor de cadena de la concatenación de todos sus nodos secundarios que se devuelven como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-123">The typed value of a complex type with complex content (one or more child elements) is the string value of the concatenation of all its child text nodes returned as a <xref:System.String>.</span></span> <span data-ttu-id="42b7d-124">Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="42b7d-124">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
- <span data-ttu-id="42b7d-125">Nombre del tipo específico del lenguaje de esquema: en la mayoría de los casos, los tipos CLR, que se establecen como un efecto secundario de la aplicación de un esquema externo, se usan para proporcionar acceso al valor de un nodo.</span><span class="sxs-lookup"><span data-stu-id="42b7d-125">Schema-Language Specific Type Name: In most cases, the CLR types, which are set as a side-effect of applying an external schema, are used to provide access to the value of a node.</span></span> <span data-ttu-id="42b7d-126">Sin embargo, puede haber situaciones en las que es conveniente examinar el tipo asociado a un esquema particular aplicado a un documento XML.</span><span class="sxs-lookup"><span data-stu-id="42b7d-126">However, there may be situations where you may want to examine the type associated with a particular schema applied to an XML document.</span></span> <span data-ttu-id="42b7d-127">Por ejemplo, podría desear realizar una búsqueda en un documento XML para extraer todos los elementos que se determine que tienen contenido del tipo "PurchaseOrder" de acuerdo con un esquema adjunto.</span><span class="sxs-lookup"><span data-stu-id="42b7d-127">For example, you may wish to search through an XML document, extracting all elements that are determined to have content of type "PurchaseOrder" according to an attached schema.</span></span> <span data-ttu-id="42b7d-128">Esa información de tipo solo se puede establecer como resultado de la validación del esquema y se tiene acceso a ella a través de las propiedades <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> y <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-128">Such type information can be set only as a result of schema validation and this information is accessed through the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> and <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="42b7d-129">Para obtener más información, vea la sección El conjunto de información posterior a la validación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="42b7d-129">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
- <span data-ttu-id="42b7d-130">Reflexión del tipo específico del lenguaje de esquema: en otros casos, es posible que quiera obtener más detalles del tipo específico del esquema que se aplica a un documento XML.</span><span class="sxs-lookup"><span data-stu-id="42b7d-130">Schema-Language Specific Type Reflection: In other cases, you may want to obtain further details of the schema-specific type applied to an XML document.</span></span> <span data-ttu-id="42b7d-131">Por ejemplo, al leer un archivo XML, puede que desee extraer el atributo `maxOccurs` para cada nodo válido del documento XML con el fin de realizar algún cálculo personalizado.</span><span class="sxs-lookup"><span data-stu-id="42b7d-131">For example, when reading an XML file, you may want to extract the `maxOccurs` attribute for each valid node in the XML document in order to perform some custom calculation.</span></span> <span data-ttu-id="42b7d-132">Puesto que esta información solo se establece a través de la validación de esquemas, se tiene acceso a ella a través de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-132">Because this information is set only through schema validation, it is accessed through the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="42b7d-133">Para obtener más información, vea la sección El conjunto de información posterior a la validación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="42b7d-133">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
## <a name="xpathnavigator-typed-accessors"></a><span data-ttu-id="42b7d-134">Descriptores de acceso con información de tipos de XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="42b7d-134">XPathNavigator Typed Accessors</span></span>  

 <span data-ttu-id="42b7d-135">En la siguiente tabla se muestran las diversas propiedades y métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se pueden utilizar para tener acceso a la información de tipo sobre un nodo.</span><span class="sxs-lookup"><span data-stu-id="42b7d-135">The following table shows the various properties and methods of the <xref:System.Xml.XPath.XPathNavigator> class that can be used to access the type information about a node.</span></span>  
  
|<span data-ttu-id="42b7d-136">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="42b7d-136">Property</span></span>|<span data-ttu-id="42b7d-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="42b7d-137">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.XmlType%2A>|<span data-ttu-id="42b7d-138">Contiene la información de tipo del esquema XML para el nodo si es válido.</span><span class="sxs-lookup"><span data-stu-id="42b7d-138">This contains the XML schema type information for the node if it is valid.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>|<span data-ttu-id="42b7d-139">Contiene el conjunto de información posterior a la validación del esquema del nodo que se agrega después de la validación.</span><span class="sxs-lookup"><span data-stu-id="42b7d-139">This contains the Post Schema Validation Infoset of the node that is added after validation.</span></span> <span data-ttu-id="42b7d-140">Esto incluye la información de tipo del esquema XML, así como la información de validez.</span><span class="sxs-lookup"><span data-stu-id="42b7d-140">This includes the XML schema type information, as well as validity information.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueType%2A>|<span data-ttu-id="42b7d-141">El tipo CLR del valor con información de tipos del nodo.</span><span class="sxs-lookup"><span data-stu-id="42b7d-141">The CLR type of the typed value of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>|<span data-ttu-id="42b7d-142">El contenido del nodo como uno o más valores CLR cuyo tipo es la coincidencia más cercana al tipo del esquema XML del nodo.</span><span class="sxs-lookup"><span data-stu-id="42b7d-142">The content of the node as one or more CLR values whose type is the closest match to the XML schema type of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsBoolean%2A>|<span data-ttu-id="42b7d-143">El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Boolean>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:boolean`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-143">The <xref:System.String> value of the current node cast to a <xref:System.Boolean> value, according to the XPath 2.0 casting rules for `xs:boolean`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDateTime%2A>|<span data-ttu-id="42b7d-144">El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.DateTime>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:datetime`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-144">The <xref:System.String> value of the current node cast to a <xref:System.DateTime> value, according to the XPath 2.0 casting rules for `xs:datetime`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>|<span data-ttu-id="42b7d-145">El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Double>, de acuerdo con las reglas de conversión de XPath 2.0 para `xsd:double`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-145">The <xref:System.String> value of the current node cast to a <xref:System.Double> value, according to the XPath 2.0 casting rules for `xsd:double`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>|<span data-ttu-id="42b7d-146">El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Int32>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:integer`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-146">The <xref:System.String> value of the current node cast to a <xref:System.Int32> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>|<span data-ttu-id="42b7d-147">El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Int64>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:integer`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-147">The <xref:System.String> value of the current node cast to a <xref:System.Int64> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAs%2A>|<span data-ttu-id="42b7d-148">El contenido del nodo convertido en el tipo de destino de acuerdo con las reglas de conversión de XPath 2.0.</span><span class="sxs-lookup"><span data-stu-id="42b7d-148">The contents of the node cast to the target type according to the XPath 2.0 casting rules.</span></span>|  
  
 <span data-ttu-id="42b7d-149">Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="42b7d-149">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="the-post-schema-validation-infoset-psvi"></a><span data-ttu-id="42b7d-150">El conjunto de información posterior a la validación de esquemas (PSVI)</span><span class="sxs-lookup"><span data-stu-id="42b7d-150">The Post Schema Validation Infoset (PSVI)</span></span>  

 <span data-ttu-id="42b7d-151">Un procesador de esquemas XML acepta un conjunto de información XML como entrada y lo convierte en un conjunto de información posterior a la validación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="42b7d-151">An XML Schema processor accepts an XML Infoset as input and converts it into a Post Schema Validation Infoset (PSVI).</span></span> <span data-ttu-id="42b7d-152">Un conjunto de información posterior a la validación de esquemas es el conjunto de información XML original en el que se han agregado nuevos elementos de información y nuevas propiedades a elementos de información existentes.</span><span class="sxs-lookup"><span data-stu-id="42b7d-152">A PSVI is the original input XML infoset with new information items added and new properties added to existing information items.</span></span> <span data-ttu-id="42b7d-153">Existen tres clases de información muy amplias que se agregan al conjunto de información XML del conjunto de información posterior a la validación de esquemas que proporciona el <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-153">There are three broad classes of information added to the XML Infoset in the PSVI that are exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
1. <span data-ttu-id="42b7d-154">Resultados de la validación: información referente a si un elemento o atributo se ha validado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="42b7d-154">Validation Outcomes: Information as to whether an element or attribute was successfully validated or not.</span></span> <span data-ttu-id="42b7d-155">Esta información la proporciona la propiedad <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-155">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
2. <span data-ttu-id="42b7d-156">Información predeterminada: indicaciones referentes a si el valor del elemento o atributo se ha obtenido o no a través de los valores predeterminados especificados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="42b7d-156">Default Information: Indications as to whether the value of the element or attribute was obtained via default values specified in the schema or not.</span></span> <span data-ttu-id="42b7d-157">Esta información la proporciona la propiedad <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-157">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
3. <span data-ttu-id="42b7d-158">Anotaciones de tipo: referencias a componentes del esquema que pueden ser definiciones de tipo o declaraciones de atributos o elementos.</span><span class="sxs-lookup"><span data-stu-id="42b7d-158">Type Annotations: References to schema components that may be type definitions or element and attribute declarations.</span></span> <span data-ttu-id="42b7d-159">La propiedad <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> de <xref:System.Xml.XPath.XPathNavigator> contiene la información de tipo específica del nodo si es válido.</span><span class="sxs-lookup"><span data-stu-id="42b7d-159">The <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property of the <xref:System.Xml.XPath.XPathNavigator> contains the specific type information of the node if it is valid.</span></span> <span data-ttu-id="42b7d-160">Si la validez del nodo es desconocida como, por ejemplo, cuándo se validó y posteriormente se editó,</span><span class="sxs-lookup"><span data-stu-id="42b7d-160">If the validity of a node is unknown, such as when it was validated then subsequently edited.</span></span> <span data-ttu-id="42b7d-161">la propiedad <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> se establece en `null` pero la información de tipo sigue estando disponible en varias propiedades de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-161">then the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property is set to `null` but type information is still available from the various properties of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 <span data-ttu-id="42b7d-162">Los siguientes ejemplos ilustran el uso de información en el conjunto de información posterior a la validación de esquemas que proporciona <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-162">The following example illustrates using information in the Post Schema Validation Infoset exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("books.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("published", "http://www.contoso.com/books")  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name)  
Console.WriteLine(navigator.SchemaInfo.Validity)  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("books.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("published", "http://www.contoso.com/books");  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name);  
Console.WriteLine(navigator.SchemaInfo.Validity);  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs);  
```  
  
 <span data-ttu-id="42b7d-163">En el ejemplo se toma como entrada el archivo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-163">The example takes the `books.xml` file as input.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="42b7d-164">En el ejemplo también se toma como entrada el esquema `books.xsd`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-164">The example also takes the `books.xsd` schema as input.</span></span>  
  
```xml  
<xs:schema xmlns="http://www.contoso.com/books"
attributeFormDefault="unqualified" elementFormDefault="qualified"
targetNamespace="http://www.contoso.com/books"
xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="publishedType">  
        <xs:restriction base="xs:date">  
            <xs:minInclusive value="2003-01-01" />  
            <xs:maxInclusive value="2003-12-31" />  
        </xs:restriction>  
    </xs:simpleType>  
    <xs:complexType name="bookType">  
        <xs:sequence>  
            <xs:element name="title" type="xs:string"/>  
            <xs:element name="price" type="xs:decimal"/>  
            <xs:element name="published" type="publishedType"/>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="booksType">  
        <xs:sequence>  
            <xs:element name="book" type="bookType" />  
        </xs:sequence>  
    </xs:complexType>  
    <xs:element name="books" type="booksType" />  
</xs:schema>  
```  
  
## <a name="obtain-typed-values-using-valueas-properties"></a><span data-ttu-id="42b7d-165">Obtención de valores con información de tipos utilizando propiedades ValueAs</span><span class="sxs-lookup"><span data-stu-id="42b7d-165">Obtain Typed Values Using ValueAs Properties</span></span>  

 <span data-ttu-id="42b7d-166">El valor con información de tipos de un nodo se puede recuperar obteniendo acceso a la propiedad <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> de <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-166">The typed value of a node can be retrieved by accessing the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="42b7d-167">En determinados casos, puede que desee convertir el valor con información de tipos de un nodo en un tipo diferente.</span><span class="sxs-lookup"><span data-stu-id="42b7d-167">In certain cases you may want to convert the typed value of a node to a different type.</span></span> <span data-ttu-id="42b7d-168">Un ejemplo muy común es la obtención de un valor numérico de un nodo XML.</span><span class="sxs-lookup"><span data-stu-id="42b7d-168">A common example is to get a numeric value from an XML node.</span></span> <span data-ttu-id="42b7d-169">Por ejemplo, considere los siguientes documentos XML no validados y sin información de tipos.</span><span class="sxs-lookup"><span data-stu-id="42b7d-169">For example, consider the following unvalidated and untyped XML document.</span></span>  
  
```xml  
<books>  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="42b7d-170">Si <xref:System.Xml.XPath.XPathNavigator> está situado en el elemento `price`, la propiedad <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> sería `null`, la propiedad <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> sería <xref:System.String> y la propiedad <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> sería la cadena `10.00`.</span><span class="sxs-lookup"><span data-stu-id="42b7d-170">If the <xref:System.Xml.XPath.XPathNavigator> is positioned on the `price` element the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property would be `null`, the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property would be <xref:System.String>, and the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property would be the string `10.00`.</span></span>  
  
 <span data-ttu-id="42b7d-171">Sin embargo, sigue siendo posible extraer el valor como un valor numérico utilizando los métodos y propiedades <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A> o <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-171">However, it is still possible to extract the value as a numeric value using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>, or <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> method and properties.</span></span> <span data-ttu-id="42b7d-172">El siguiente ejemplo ilustra la realización de dicha conversión utilizando el método <xref:System.Xml.XPath.XPathItem.ValueAs%2A>.</span><span class="sxs-lookup"><span data-stu-id="42b7d-172">The following example illustrates performing such a cast using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A> method.</span></span>  
  
```vb  
Dim document As New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "")  
navigator.MoveToChild("book", "")  
navigator.MoveToChild("price", "")  
  
Dim price = navigator.ValueAs(GetType(Decimal))  
Dim discount As Decimal = 0.2  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * discount))  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "");  
navigator.MoveToChild("book", "");  
navigator.MoveToChild("price", "");  
  
Decimal price = (decimal)navigator.ValueAs(typeof(decimal));  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * (decimal)0.20));  
```  
  
 <span data-ttu-id="42b7d-173">Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="42b7d-173">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b7d-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="42b7d-174">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="42b7d-175">Compatibilidad de tipos en las clases System.Xml</span><span class="sxs-lookup"><span data-stu-id="42b7d-175">Type Support in the System.Xml Classes</span></span>](type-support-in-the-system-xml-classes.md)
- [<span data-ttu-id="42b7d-176">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="42b7d-176">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="42b7d-177">Navegación por un conjunto de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="42b7d-177">Node Set Navigation Using XPathNavigator</span></span>](node-set-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="42b7d-178">Navegación por nodos de espacios de nombres y atributos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="42b7d-178">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="42b7d-179">Extracción de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="42b7d-179">Extract XML Data Using XPathNavigator</span></span>](extract-xml-data-using-xpathnavigator.md)
