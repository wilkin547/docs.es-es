---
title: Cómo quitar datos XML con XPathNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f436bca-1b96-494b-a6d2-e102c7551752
ms.openlocfilehash: 0895154e6932f32ebd3f5d1cf0d59bd557eb1b06
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822547"
---
# <a name="remove-xml-data-using-xpathnavigator"></a><span data-ttu-id="5cb04-102">Cómo quitar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="5cb04-102">Remove XML Data using XPathNavigator</span></span>
<span data-ttu-id="5cb04-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para quitar nodos y valores de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="5cb04-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="5cb04-104">Para utilizar estos métodos, el objeto <xref:System.Xml.XPath.XPathNavigator> debe ser editable, es decir, su propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> debe ser `true`.</span><span class="sxs-lookup"><span data-stu-id="5cb04-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="5cb04-105">El método <xref:System.Xml.XPath.XPathNavigator> de la clase <xref:System.Xml.XmlDocument.CreateNavigator%2A> crea los objetos <xref:System.Xml.XmlDocument> que pueden editar un documento XML.</span><span class="sxs-lookup"><span data-stu-id="5cb04-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="5cb04-106">Los objetos <xref:System.Xml.XPath.XPathNavigator> que crea la clase <xref:System.Xml.XPath.XPathDocument> son de solo lectura y cualquier intento de utilizar los métodos de edición de un objeto <xref:System.Xml.XPath.XPathNavigator> creado por un objeto <xref:System.Xml.XPath.XPathDocument> producirá una excepción <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="5cb04-107">Para más información sobre cómo crear objetos <xref:System.Xml.XPath.XPathNavigator> editables, vea [Lectura de datos XML con XPathDocument y XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="removing-nodes"></a><span data-ttu-id="5cb04-108">Cómo quitar nodos</span><span class="sxs-lookup"><span data-stu-id="5cb04-108">Removing Nodes</span></span>  
 <span data-ttu-id="5cb04-109">La clase <xref:System.Xml.XPath.XPathNavigator> incluye el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> para quitar nodos de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="5cb04-109">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to remove nodes from an XML document.</span></span>  
  
### <a name="removing-a-node"></a><span data-ttu-id="5cb04-110">Cómo quitar un nodo</span><span class="sxs-lookup"><span data-stu-id="5cb04-110">Removing a Node</span></span>  
 <span data-ttu-id="5cb04-111">La clase <xref:System.Xml.XPath.XPathNavigator> incluye el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> para eliminar el nodo actual en el que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator> de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="5cb04-111">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method to delete the current node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on from an XML document.</span></span>  
  
 <span data-ttu-id="5cb04-112">Una vez eliminado un nodo con el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>, ya no se puede llegar a él desde la raíz del objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-112">After a node has been deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method, it is no longer reachable from the root of the <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="5cb04-113">Una vez eliminado un nodo, <xref:System.Xml.XPath.XPathNavigator> se sitúa en el nodo primario del nodo eliminado.</span><span class="sxs-lookup"><span data-stu-id="5cb04-113">After a node has been deleted, the <xref:System.Xml.XPath.XPathNavigator> is positioned on the parent node of the deleted node.</span></span>  
  
 <span data-ttu-id="5cb04-114">La operación de eliminación no afecta a la posición de ningún objeto <xref:System.Xml.XPath.XPathNavigator> situado en el nodo eliminado.</span><span class="sxs-lookup"><span data-stu-id="5cb04-114">A delete operation doesn't affect the position of any <xref:System.Xml.XPath.XPathNavigator> object positioned on the deleted node.</span></span> <span data-ttu-id="5cb04-115">Estos objetos <xref:System.Xml.XPath.XPathNavigator> son válidos en el sentido de que se pueden mover en el subárbol eliminado, pero no se pueden mover al árbol del nodo principal utilizando los métodos normales de navegación por conjuntos de nodos de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-115">These <xref:System.Xml.XPath.XPathNavigator> objects are valid in the sense that they can move within the deleted subtree, but cannot be moved to the main node tree using the regular node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5cb04-116">El método <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> se puede utilizar para mover estos objetos <xref:System.Xml.XPath.XPathNavigator> de nuevo al árbol del nodo principal, o desde el árbol del nodo principal al subárbol eliminado.</span><span class="sxs-lookup"><span data-stu-id="5cb04-116">The <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class can be used to move these <xref:System.Xml.XPath.XPathNavigator> objects back into the main node tree, or from the main node tree to the deleted subtree.</span></span>  
  
 <span data-ttu-id="5cb04-117">En el siguiente ejemplo se elimina el elemento `price` del primer elemento `book` del archivo `contosoBooks.xml` utilizando el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-117">In the following example, the `price` element of the first `book` element of the `contosoBooks.xml` file is deleted using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span> <span data-ttu-id="5cb04-118">La posición del objeto <xref:System.Xml.XPath.XPathNavigator> después de eliminar el elemento `price` se encuentra en el elemento `book` primario.</span><span class="sxs-lookup"><span data-stu-id="5cb04-118">The position of the <xref:System.Xml.XPath.XPathNavigator> object after the `price` element is deleted is on the parent `book` element.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.DeleteSelf()  
  
Console.WriteLine("Position after delete: {0}", navigator.Name)  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.DeleteSelf();  
  
Console.WriteLine("Position after delete: {0}", navigator.Name);  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="5cb04-119">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="5cb04-119">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-an-attribute-node"></a><span data-ttu-id="5cb04-120">Cómo quitar un nodo de atributos</span><span class="sxs-lookup"><span data-stu-id="5cb04-120">Removing an Attribute Node</span></span>  
 <span data-ttu-id="5cb04-121">Los nodos de atributos se quitan de un documento XML utilizando el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-121">Attribute nodes are removed from an XML document using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method.</span></span>  
  
 <span data-ttu-id="5cb04-122">Después de eliminar un nodo de atributos, ya no se puede llegar a él desde el nodo raíz de un objeto <xref:System.Xml.XmlDocument> y el objeto <xref:System.Xml.XPath.XPathNavigator> se sitúa en el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="5cb04-122">After an attribute node has been deleted, it is no longer reachable from the root node of an <xref:System.Xml.XmlDocument> object and the <xref:System.Xml.XPath.XPathNavigator> object is positioned on the parent element.</span></span>  
  
#### <a name="default-attributes"></a><span data-ttu-id="5cb04-123">Atributos predeterminados</span><span class="sxs-lookup"><span data-stu-id="5cb04-123">Default Attributes</span></span>  
 <span data-ttu-id="5cb04-124">Con independencia del método que se utilice para quitar atributos, existen unas limitaciones especiales para quitar atributos que se hayan definido como predeterminados en la DTD o el esquema XML del documento XML.</span><span class="sxs-lookup"><span data-stu-id="5cb04-124">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the DTD or XML Schema for the XML document.</span></span> <span data-ttu-id="5cb04-125">Los atributos predeterminados no se pueden quitar a menos que se quite también el elemento al que pertenecen.</span><span class="sxs-lookup"><span data-stu-id="5cb04-125">Default attributes cannot be removed unless the element they belong to is also removed.</span></span> <span data-ttu-id="5cb04-126">Los atributos predeterminados siempre están presentes en los elementos que los tengan declarados y, como resultado, al eliminar un atributo predeterminado, se inserta un atributo de reemplazo en el elemento y se inicializa en el valor predeterminado que se haya declarado.</span><span class="sxs-lookup"><span data-stu-id="5cb04-126">Default attributes are always present for elements that have default attributes declared, and as a result, deleting a default attribute results in a replacement attribute being inserted into the element and initialized to the default value that was declared.</span></span>  
  
## <a name="removing-values"></a><span data-ttu-id="5cb04-127">Cómo quitar valores</span><span class="sxs-lookup"><span data-stu-id="5cb04-127">Removing Values</span></span>  
 <span data-ttu-id="5cb04-128">La clase <xref:System.Xml.XPath.XPathNavigator> incluye los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> para quitar valores con y sin información de tipos de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="5cb04-128">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to remove untyped and typed values from an XML document.</span></span>  
  
### <a name="removing-untyped-values"></a><span data-ttu-id="5cb04-129">Cómo quitar valores sin información de tipos</span><span class="sxs-lookup"><span data-stu-id="5cb04-129">Removing Untyped Values</span></span>  
 <span data-ttu-id="5cb04-130">El método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> simplemente inserta el valor `string` sin información de tipos, que se pasa como parámetro, como valor del nodo en el que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-130">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="5cb04-131">Al pasar una cadena vacía al método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>, se quita el valor del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="5cb04-131">Passing an empty string to the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method removes the value of the current node.</span></span>  
  
 <span data-ttu-id="5cb04-132">En el siguiente ejemplo, se quita el valor del elemento `price` del primer elemento `book` en el archivo `contosoBooks.xml` utilizando el método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-132">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetValue("")  
  
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
  
navigator.SetValue("");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 <span data-ttu-id="5cb04-133">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="5cb04-133">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-typed-values"></a><span data-ttu-id="5cb04-134">Cómo quitar valores con información de tipos</span><span class="sxs-lookup"><span data-stu-id="5cb04-134">Removing Typed Values</span></span>  
 <span data-ttu-id="5cb04-135">Cuando un nodo es de un tipo simple de esquema XML del W3C, el valor nuevo que ha insertado el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> se comprueba en las facetas del tipo simple antes de establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="5cb04-135">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="5cb04-136">Si el valor nuevo no es válido de acuerdo con el tipo del nodo (por ejemplo, si se establece un valor de `-1` en un elemento cuyo tipo es `xs:positiveInteger`), se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="5cb04-136">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span> <span data-ttu-id="5cb04-137">El método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> tampoco se puede pasar `null` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="5cb04-137">The <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method also cannot be passed `null` as a parameter.</span></span> <span data-ttu-id="5cb04-138">Como resultado, al quitar el valor de un nodo con tipo, se debe cumplir el tipo de esquema del nodo.</span><span class="sxs-lookup"><span data-stu-id="5cb04-138">As a result removing the value of a typed node must comply with the schema type of the node.</span></span>  
  
 <span data-ttu-id="5cb04-139">En el siguiente ejemplo, se quita el valor del elemento `price` del primer elemento `book` en el archivo `contosoBooks.xml` con el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> estableciendo el valor en `0`.</span><span class="sxs-lookup"><span data-stu-id="5cb04-139">The following example removes the value of the `price` element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method by setting the value to `0`.</span></span> <span data-ttu-id="5cb04-140">El valor del nodo no se quita, pero sí el precio del libro de acuerdo con su tipo de datos de `xs:decimal`.</span><span class="sxs-lookup"><span data-stu-id="5cb04-140">The value of the node is not removed, but the price of the book has been removed according to its data type of `xs:decimal`.</span></span>  
  
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
  
navigator.SetTypedValue(0)  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
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
  
navigator.SetTypedValue(0);  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
## <a name="namespace-nodes"></a><span data-ttu-id="5cb04-141">Nodos de espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="5cb04-141">Namespace Nodes</span></span>  
 <span data-ttu-id="5cb04-142">Los nodos de espacios de nombres no se pueden eliminar de un objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-142">Namespace nodes cannot be deleted from an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="5cb04-143">Si se intenta eliminar nodos de espacios de nombres con el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="5cb04-143">Attempts to delete namespace nodes using the <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> method results in an exception.</span></span>  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="5cb04-144">Propiedades InnerXml y OuterXml</span><span class="sxs-lookup"><span data-stu-id="5cb04-144">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="5cb04-145">Las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> cambian el marcado XML de los nodos en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-145">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="5cb04-146">La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator> por el contenido analizado de la `string` XML especificada.</span><span class="sxs-lookup"><span data-stu-id="5cb04-146">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="5cb04-147">Igualmente, la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, así como el propio nodo actual.</span><span class="sxs-lookup"><span data-stu-id="5cb04-147">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="5cb04-148">Además de los métodos que se describen en este tema, se pueden utilizar las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para quitar nodos y valores de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="5cb04-148">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to remove nodes and values from an XML document.</span></span> <span data-ttu-id="5cb04-149">Para más información sobre el uso de las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para modificar nodos, vea el tema [Modificación de datos XML con XPathNavigator](modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-149">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to modify nodes, see the [Modify XML Data using XPathNavigator](modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="5cb04-150">Cómo guardar un documento XML</span><span class="sxs-lookup"><span data-stu-id="5cb04-150">Saving an XML Document</span></span>  
 <span data-ttu-id="5cb04-151">Para guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument> como resultado de los métodos que se describen en este tema, se utilizan los métodos de la clase <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="5cb04-151">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="5cb04-152">Para obtener más información sobre cómo guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument>, vea [Guardar y escribir un documento](saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="5cb04-152">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb04-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cb04-153">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="5cb04-154">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="5cb04-154">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="5cb04-155">Inserción de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="5cb04-155">Insert XML Data using XPathNavigator</span></span>](insert-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="5cb04-156">Modificación de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="5cb04-156">Modify XML Data using XPathNavigator</span></span>](modify-xml-data-using-xpathnavigator.md)
