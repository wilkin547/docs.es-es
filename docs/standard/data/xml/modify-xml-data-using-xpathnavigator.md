---
title: Modificación de datos XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 03a7c5a1-b296-4af4-b209-043c958dc0a5
ms.openlocfilehash: 3b64bc8666274798ebaefc87ef3883fcec1ef6b1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288841"
---
# <a name="modify-xml-data-using-xpathnavigator"></a><span data-ttu-id="c6af0-102">Modificación de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c6af0-102">Modify XML Data using XPathNavigator</span></span>
<span data-ttu-id="c6af0-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para modificar nodos y valores en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="c6af0-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to modify nodes and values in an XML document.</span></span> <span data-ttu-id="c6af0-104">Para utilizar estos métodos, el objeto <xref:System.Xml.XPath.XPathNavigator> debe ser editable, es decir, su propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> debe ser `true`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="c6af0-105">El método <xref:System.Xml.XPath.XPathNavigator> de la clase <xref:System.Xml.XmlDocument.CreateNavigator%2A> crea los objetos <xref:System.Xml.XmlDocument> que pueden editar un documento XML.</span><span class="sxs-lookup"><span data-stu-id="c6af0-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="c6af0-106">Los objetos <xref:System.Xml.XPath.XPathNavigator> que crea la clase <xref:System.Xml.XPath.XPathDocument> son de solo lectura y cualquier intento de utilizar los métodos de edición de un objeto <xref:System.Xml.XPath.XPathNavigator> creado por un objeto <xref:System.Xml.XPath.XPathDocument> producirá una excepción <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object result in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="c6af0-107">Para más información sobre cómo crear objetos <xref:System.Xml.XPath.XPathNavigator> editables, vea [Lectura de datos XML con XPathDocument y XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="c6af0-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="modifying-nodes"></a><span data-ttu-id="c6af0-108">Modificación de nodos</span><span class="sxs-lookup"><span data-stu-id="c6af0-108">Modifying Nodes</span></span>  
 <span data-ttu-id="c6af0-109">Una técnica muy sencilla para cambiar el valor de un nodo consiste en utilizar los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-109">A simple technique for changing the value of a node is to use the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 <span data-ttu-id="c6af0-110">En la siguiente tabla se enumeran los efectos de estos métodos en diferentes tipos de nodos.</span><span class="sxs-lookup"><span data-stu-id="c6af0-110">The following table lists the effects of these methods on different node types.</span></span>  
  
|<xref:System.Xml.XPath.XPathNodeType>|<span data-ttu-id="c6af0-111">Datos cambiados</span><span class="sxs-lookup"><span data-stu-id="c6af0-111">Data Changed</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------------------|------------------|  
|<xref:System.Xml.XPath.XPathNodeType.Root>|<span data-ttu-id="c6af0-112">No se admite.</span><span class="sxs-lookup"><span data-stu-id="c6af0-112">Not supported.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Element>|<span data-ttu-id="c6af0-113">El contenido del elemento.</span><span class="sxs-lookup"><span data-stu-id="c6af0-113">The content of the element.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Attribute>|<span data-ttu-id="c6af0-114">El valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="c6af0-114">The value of the attribute.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Text>|<span data-ttu-id="c6af0-115">Contenido de texto.</span><span class="sxs-lookup"><span data-stu-id="c6af0-115">The text content.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>|<span data-ttu-id="c6af0-116">El contenido, sin incluir el destino.</span><span class="sxs-lookup"><span data-stu-id="c6af0-116">The content, excluding the target.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Comment>|<span data-ttu-id="c6af0-117">El contenido del comentario.</span><span class="sxs-lookup"><span data-stu-id="c6af0-117">The content of the comment.</span></span>|  
|<xref:System.Xml.XPath.XPathNodeType.Namespace>|<span data-ttu-id="c6af0-118">No admitido.</span><span class="sxs-lookup"><span data-stu-id="c6af0-118">Not Supported.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c6af0-119">No se permite editar los nodos <xref:System.Xml.XPath.XPathNodeType.Namespace> ni el nodo <xref:System.Xml.XPath.XPathNodeType.Root>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-119">Editing <xref:System.Xml.XPath.XPathNodeType.Namespace> nodes or the <xref:System.Xml.XPath.XPathNodeType.Root> node is not supported.</span></span>  
  
 <span data-ttu-id="c6af0-120">La clase <xref:System.Xml.XPath.XPathNavigator> también incluye un conjunto de métodos que se utilizan para insertar y quitar nodos.</span><span class="sxs-lookup"><span data-stu-id="c6af0-120">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of methods used to insert and remove nodes.</span></span> <span data-ttu-id="c6af0-121">Para más información sobre cómo insertar y quitar nodos de un documento XML, vea los temas [Inserción de datos XML con XPathNavigator](insert-xml-data-using-xpathnavigator.md) y [Cómo quitar datos XML con XPathNavigator](remove-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="c6af0-121">For more information about inserting and removing nodes from an XML document, see the [Insert XML Data using XPathNavigator](insert-xml-data-using-xpathnavigator.md) and [Remove XML Data using XPathNavigator](remove-xml-data-using-xpathnavigator.md) topics.</span></span>  
  
### <a name="modifying-untyped-values"></a><span data-ttu-id="c6af0-122">Modificación de valores sin información de tipos</span><span class="sxs-lookup"><span data-stu-id="c6af0-122">Modifying Untyped Values</span></span>  
 <span data-ttu-id="c6af0-123">El método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> simplemente inserta el valor `string` sin información de tipos, que se pasa como parámetro, como valor del nodo en el que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-123">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="c6af0-124">Este valor se inserta sin ningún tipo o sin comprobar si el nuevo valor es válido de acuerdo con el tipo del nodo si hay disponible información de esquema.</span><span class="sxs-lookup"><span data-stu-id="c6af0-124">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="c6af0-125">En el siguiente ejemplo, el método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> se utiliza para actualizar todos los elementos `price` del archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-125">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="c6af0-126">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-126">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="modifying-typed-values"></a><span data-ttu-id="c6af0-127">Modificación de valores con información de tipos</span><span class="sxs-lookup"><span data-stu-id="c6af0-127">Modifying Typed Values</span></span>  
 <span data-ttu-id="c6af0-128">Cuando un nodo es de un tipo simple de esquema XML del W3C, el valor nuevo que ha insertado el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> se comprueba en las facetas del tipo simple antes de establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="c6af0-128">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="c6af0-129">Si el valor nuevo no es válido de acuerdo con el tipo del nodo (por ejemplo, si se establece un valor de `-1` en un elemento cuyo tipo es `xs:positiveInteger`), se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="c6af0-129">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="c6af0-130">En el siguiente ejemplo se intenta cambiar el valor del elemento `price` del primer elemento `book` en el archivo `contosoBooks.xml` por un valor <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-130">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="c6af0-131">Dado que el tipo de esquema XML del elemento `price` está definido como `xs:decimal` en los archivos `contosoBooks.xsd`, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="c6af0-131">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(DateTime.Now)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="c6af0-132">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-132">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="c6af0-133">En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-133">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
#### <a name="the-effects-of-editing-strongly-typed-xml-data"></a><span data-ttu-id="c6af0-134">Efectos de la edición de datos XML fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="c6af0-134">The Effects of Editing Strongly Typed XML Data</span></span>  
 <span data-ttu-id="c6af0-135">La clase <xref:System.Xml.XPath.XPathNavigator> usa el esquema XML del W3C como base para describir XML fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="c6af0-135">The <xref:System.Xml.XPath.XPathNavigator> class uses the W3C XML Schema as a basis for describing strongly typed XML.</span></span> <span data-ttu-id="c6af0-136">Se pueden anotar los elementos y atributos con la información de tipos basándose en la validación realizada en un documento de esquema XML del W3C.</span><span class="sxs-lookup"><span data-stu-id="c6af0-136">Elements and attributes can be annotated with type information based on validation against a W3C XML Schema document.</span></span> <span data-ttu-id="c6af0-137">Los elementos que pueden contener otros elementos o atributos se denominan tipos complejos, mientras que los que solo pueden incluir contenido textual, se denominan tipos simples.</span><span class="sxs-lookup"><span data-stu-id="c6af0-137">Elements that can contain other elements or attributes are called complex types, while those that can only contain textual content are called simple types.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6af0-138">Los atributos solo pueden tener tipos simples.</span><span class="sxs-lookup"><span data-stu-id="c6af0-138">Attributes can only have simple types.</span></span>  
  
 <span data-ttu-id="c6af0-139">Se considera que un elemento o atributo tiene un esquema válido si cumple todas las normas específicas a la definición de su tipo.</span><span class="sxs-lookup"><span data-stu-id="c6af0-139">An element or attribute can be considered to be schema-valid if it conforms to all the rules specific to its type definition.</span></span> <span data-ttu-id="c6af0-140">Un elemento que tenga el tipo simple `xs:int` debe contener un valor numérico entre -2147483648 y 2147483647 para que su esquema sea válido.</span><span class="sxs-lookup"><span data-stu-id="c6af0-140">An element that has the simple type `xs:int` has to contain a numeric value between -2147483648 and 2147483647 to be schema-valid.</span></span> <span data-ttu-id="c6af0-141">En los tipos complejos, la validez del esquema del elemento depende de la validez del esquema de sus elementos y atributos secundarios.</span><span class="sxs-lookup"><span data-stu-id="c6af0-141">For complex types, the schema-validity of the element is dependent on the schema-validity of its child elements and attributes.</span></span> <span data-ttu-id="c6af0-142">De esta manera, si un elemento es válido de acuerdo con la definición de su tipo complejo, todos sus elementos y atributos secundarios son válidos de acuerdo con las definiciones de sus tipos.</span><span class="sxs-lookup"><span data-stu-id="c6af0-142">Thus if an element is valid against its complex type definition, all its child elements and attributes are valid against their type definitions.</span></span> <span data-ttu-id="c6af0-143">De igual forma, si tan solo uno de los elementos o atributos secundarios de un elemento no es válido de acuerdo con la definición de su tipo, o tiene una validez desconocida, dicho elemento tampoco es válido o también tiene una validez desconocida.</span><span class="sxs-lookup"><span data-stu-id="c6af0-143">Similarly, if even one of the child elements or attributes of an element is invalid against its type definition, or has an unknown validity, the element is also either invalid or of unknown validity.</span></span>  
  
 <span data-ttu-id="c6af0-144">Dado que la validez de un elemento depende de la validez de sus elementos y atributos secundarios, las modificaciones que se realicen en cualquiera de ellos cambian la validez del elemento si previamente era válido.</span><span class="sxs-lookup"><span data-stu-id="c6af0-144">Given that the validity of an element is dependent on the validity of its child elements and attributes, modifications to either result in altering the validity of the element if it was previously valid.</span></span> <span data-ttu-id="c6af0-145">Concretamente, si se insertan, actualizan o eliminan elementos o atributos secundarios de un elemento, la validez de dicho elemento pasa a ser desconocida.</span><span class="sxs-lookup"><span data-stu-id="c6af0-145">Specifically, if the child elements or attributes of an element are inserted, updated, or deleted, then the validity of the element becomes unknown.</span></span> <span data-ttu-id="c6af0-146">Esto lo representa la propiedad <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> del elemento que se establece en <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-146">This is represented by the <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> property of the element's <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property being set to <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown>.</span></span> <span data-ttu-id="c6af0-147">Asimismo, esto tiene un efecto en cascada ascendente y recursivo en todo el documento XML, porque la validez del elemento primario del elemento (y de su elemento primario y así, sucesivamente) también pasa a ser desconocida.</span><span class="sxs-lookup"><span data-stu-id="c6af0-147">Furthermore, this effect cascades upwards recursively across the XML document, because the validity of the element's parent element (and its parent element, and so on) also becomes unknown.</span></span>  
  
 <span data-ttu-id="c6af0-148">Para más información sobre la validación de esquemas y la clase <xref:System.Xml.XPath.XPathNavigator>, vea [Validación de esquemas con XPathNavigator](schema-validation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="c6af0-148">For more information about schema validation and the <xref:System.Xml.XPath.XPathNavigator> class, see [Schema Validation using XPathNavigator](schema-validation-using-xpathnavigator.md).</span></span>  
  
### <a name="modifying-attributes"></a><span data-ttu-id="c6af0-149">Modificación de atributos</span><span class="sxs-lookup"><span data-stu-id="c6af0-149">Modifying Attributes</span></span>  
 <span data-ttu-id="c6af0-150">Los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> pueden utilizarse para modificar nodos de atributos con y sin información de tipos, así como los otros tipos de nodos que se enumeran en la sección "Modificación de nodos".</span><span class="sxs-lookup"><span data-stu-id="c6af0-150">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods can be used to modify untyped and typed attribute nodes as well as the other node types listed in the "Modifying Nodes" section.</span></span>  
  
 <span data-ttu-id="c6af0-151">En el siguiente ejemplo se cambia el valor del atributo `genre` del primer elemento `book` en el archivo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-151">The following example changes the value of the `genre` attribute of the first `book` element in the `books.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
navigator.MoveToChild("book", String.Empty)  
navigator.MoveToAttribute("genre", String.Empty)  
  
navigator.SetValue("non-fiction")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
navigator.MoveToChild("book", String.Empty);  
navigator.MoveToAttribute("genre", String.Empty);  
  
navigator.SetValue("non-fiction");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="c6af0-152">Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, vea las secciones "Modificación de valores sin información de tipos" y "Modificación de valores con información de tipos".</span><span class="sxs-lookup"><span data-stu-id="c6af0-152">For more information about the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods, see the "Modifying Untyped Values" and "Modifying Typed Values" sections.</span></span>  
  
## <a name="innerxml-and-outerxml-properties"></a><span data-ttu-id="c6af0-153">Propiedades InnerXml y OuterXml</span><span class="sxs-lookup"><span data-stu-id="c6af0-153">InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="c6af0-154">Las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> cambian el marcado XML de los nodos en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-154">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="c6af0-155">La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator> por el contenido analizado de la `string` XML especificada.</span><span class="sxs-lookup"><span data-stu-id="c6af0-155">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="c6af0-156">Igualmente, la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, así como el propio nodo actual.</span><span class="sxs-lookup"><span data-stu-id="c6af0-156">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="c6af0-157">En el siguiente ejemplo se utiliza la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para modificar el valor del elemento `price` e insertar un nuevo atributo `discount` en el primer elemento `book` del archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-157">The following example uses the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property to modify the value of the `price` element and insert a new `discount` attribute on the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml");  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>"  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>";  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="c6af0-158">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-158">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
## <a name="modifying-namespace-nodes"></a><span data-ttu-id="c6af0-159">Modificación de nodos de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="c6af0-159">Modifying Namespace Nodes</span></span>  
 <span data-ttu-id="c6af0-160">En el Modelo de objetos de documento (DOM), las declaraciones de espacios de nombres se tratan como si fueran atributos normales que se pueden insertar, actualizar y eliminar.</span><span class="sxs-lookup"><span data-stu-id="c6af0-160">In the Document Object Model (DOM), namespace declarations are treated as if they are regular attributes that can be inserted, updated and deleted.</span></span> <span data-ttu-id="c6af0-161">La clase <xref:System.Xml.XPath.XPathNavigator> no permite realizar estas operaciones en nodos de espacios de nombres ya que, si se cambia el valor de un nodo de espacio de nombres, puede cambiar la identidad de los elementos y atributos en el ámbito del nodo de espacio de nombres, tal y como se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c6af0-161">The <xref:System.Xml.XPath.XPathNavigator> class does not allow such operations on namespace nodes because altering the value of a namespace node can change the identity of the elements and attributes within the scope of the namespace node as illustrated in the following example.</span></span>  
  
```xml  
<root xmlns="http://www.contoso.com">  
    <child />  
</root>  
```  
  
 <span data-ttu-id="c6af0-162">Si se cambia el ejemplo de XML anterior de la siguiente manera, cambiará el nombre de todos los elementos del documento de manera efectiva, ya que se cambia el valor del identificador URI del espacio de nombres de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="c6af0-162">If the XML example above is changed in the following way, this effectively renames every element in the document because the value of each element's namespace URI is changed.</span></span>  
  
```xml  
<root xmlns="urn:contoso.com">  
    <child />  
</root>  
```  
  
 <span data-ttu-id="c6af0-163">La clase <xref:System.Xml.XPath.XPathNavigator> permite insertar nodos de espacios de nombres que no entren en conflicto con las declaraciones de espacios de nombres en el ámbito en el que se insertan.</span><span class="sxs-lookup"><span data-stu-id="c6af0-163">Inserting namespace nodes that do not conflict with namespace declarations at the scope that they are inserted in is allowed by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="c6af0-164">En este caso, las declaraciones de espacios de nombres no se declaran en ámbitos inferiores del documento XML y no se produce el cambio de nombres, tal y como se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c6af0-164">In this case, the namespace declarations are not declared at lower scopes in the XML document and does not result in renaming as illustrated in the following example.</span></span>  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent>  
        <a:child />  
    </parent>  
</root>  
```  
  
 <span data-ttu-id="c6af0-165">Si el ejemplo de XML anterior se cambia de la siguiente forma, las declaraciones de espacios de nombres se propagan correctamente por el documento XML por debajo del ámbito de la otra declaración de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c6af0-165">If the XML example above is changed in the following way, the namespace declarations are correctly propagated across the XML document below the scope of the other namespace declaration.</span></span>  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent a:parent-id="1234" xmlns:a="http://www.contoso.com/parent-id">  
        <a:child xmlns:a="http://www.contoso.com/" />  
    </parent>  
</root>  
```  
  
 <span data-ttu-id="c6af0-166">En el ejemplo de XML anterior, se inserta el atributo `a:parent-id` en el elemento `parent` del espacio de nombres `http://www.contoso.com/parent-id`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-166">In the XML example above, the attribute `a:parent-id` is inserted on the `parent` element in the `http://www.contoso.com/parent-id` namespace.</span></span> <span data-ttu-id="c6af0-167">Se utiliza el método <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> para insertar el atributo mientras se encuentra situado en el elemento `parent`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-167">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method is used to insert the attribute while positioned on the `parent` element.</span></span> <span data-ttu-id="c6af0-168">La clase `http://www.contoso.com` inserta automáticamente la declaración de espacio de nombres <xref:System.Xml.XPath.XPathNavigator> para mantener la coherencia del resto del documento XML.</span><span class="sxs-lookup"><span data-stu-id="c6af0-168">The `http://www.contoso.com` namespace declaration is automatically inserted by the <xref:System.Xml.XPath.XPathNavigator> class to preserve the consistency of the rest of the XML document.</span></span>  
  
## <a name="modifying-entity-reference-nodes"></a><span data-ttu-id="c6af0-169">Modificación de nodos de referencia de entidad</span><span class="sxs-lookup"><span data-stu-id="c6af0-169">Modifying Entity Reference Nodes</span></span>  
 <span data-ttu-id="c6af0-170">Los nodos de referencia de entidad de un objeto <xref:System.Xml.XmlDocument> son de solo lectura y no se pueden editar con las clases <xref:System.Xml.XPath.XPathNavigator> o <xref:System.Xml.XmlNode>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-170">Entity reference nodes in an <xref:System.Xml.XmlDocument> object are read-only and cannot be edited using either the <xref:System.Xml.XPath.XPathNavigator> or <xref:System.Xml.XmlNode> classes.</span></span> <span data-ttu-id="c6af0-171">Cualquier intento de modificar un nodo de referencia de entidad produce una <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-171">Any attempt to modify an entity reference node results in an <xref:System.InvalidOperationException>.</span></span>  
  
## <a name="modifying-xsinil-nodes"></a><span data-ttu-id="c6af0-172">Modificación de nodos xsi:nil</span><span class="sxs-lookup"><span data-stu-id="c6af0-172">Modifying xsi:nil Nodes</span></span>  
 <span data-ttu-id="c6af0-173">La recomendación del esquema XML del W3C introduce el concepto de elemento "nillable".</span><span class="sxs-lookup"><span data-stu-id="c6af0-173">The W3C XML Schema recommendation introduces the concept of an element being nillable.</span></span> <span data-ttu-id="c6af0-174">Cuando un elemento es "nillable", es posible que sea válido sin tener contenido.</span><span class="sxs-lookup"><span data-stu-id="c6af0-174">When an element is nillable, it is possible for the element to have no content and still be valid.</span></span> <span data-ttu-id="c6af0-175">El concepto de elemento "nillable" es similar al concepto de objeto `null`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-175">The concept of an element being nillable is similar to the concept of an object being `null`.</span></span> <span data-ttu-id="c6af0-176">La principal diferencia es que no es posible obtener acceso de ninguna forma a un objeto `null`, mientras que un elemento `xsi:nil` sigue teniendo propiedades (por ejemplo, atributos) a las que se puede tener acceso, pero no tiene contenido (es decir, texto ni elementos secundarios).</span><span class="sxs-lookup"><span data-stu-id="c6af0-176">The main difference is that a `null` object cannot be accessed in any way, while an `xsi:nil` element still has properties such as attributes that can be accessed, but has no content (child elements or text).</span></span> <span data-ttu-id="c6af0-177">La existencia del atributo `xsi:nil` con un valor de `true` en un elemento de un documento XML se utiliza para indicar que un elemento no tiene contenido.</span><span class="sxs-lookup"><span data-stu-id="c6af0-177">The existence of the `xsi:nil` attribute with a value of `true` on an element in an XML document is used to indicate that an element has no content.</span></span>  
  
 <span data-ttu-id="c6af0-178">Si se utiliza un objeto <xref:System.Xml.XPath.XPathNavigator> para agregar contenido a un elemento válido con un atributo `xsi:nil` que tiene un valor de `true`, el valor de su atributo `xsi:nil` se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-178">If an <xref:System.Xml.XPath.XPathNavigator> object is used to add content to a valid element with an `xsi:nil` attribute with a value of `true`, the value of its `xsi:nil` attribute is set to `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6af0-179">Si se elimina el contenido de un elemento con un atributo `xsi:nil` establecido en `false`, el valor del atributo no se cambia por `true`.</span><span class="sxs-lookup"><span data-stu-id="c6af0-179">If the content of an element with an `xsi:nil` attribute set to `false` is deleted, the value of the attribute is not changed to `true`.</span></span>  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="c6af0-180">Cómo guardar un documento XML</span><span class="sxs-lookup"><span data-stu-id="c6af0-180">Saving an XML Document</span></span>  
 <span data-ttu-id="c6af0-181">Para guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument> como resultado de los métodos de edición que se describen en este tema, se utilizan los métodos de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="c6af0-181">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the editing methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="c6af0-182">Para obtener más información sobre cómo guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument>, vea [Guardar y escribir un documento](saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="c6af0-182">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6af0-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6af0-183">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="c6af0-184">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="c6af0-184">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="c6af0-185">Inserción de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c6af0-185">Insert XML Data using XPathNavigator</span></span>](insert-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="c6af0-186">Eliminación de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c6af0-186">Remove XML Data using XPathNavigator</span></span>](remove-xml-data-using-xpathnavigator.md)
