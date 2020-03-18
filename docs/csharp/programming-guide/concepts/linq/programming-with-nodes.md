---
title: Programar con nodos (C#)
ms.date: 07/20/2015
ms.assetid: c38df0f2-c805-431a-93ff-9103a4284c2f
ms.openlocfilehash: 05c2e95fe97effda7b537a7ac2d8f5780f4e212b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168319"
---
# <a name="programming-with-nodes-c"></a><span data-ttu-id="25e87-102">Programar con nodos (C#)</span><span class="sxs-lookup"><span data-stu-id="25e87-102">Programming with Nodes (C#)</span></span>
<span data-ttu-id="25e87-103">Los desarrolladores de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] que deben escribir programar como un editor de XML, un sistema de transformación o un sistema de escritura de informes a menudo deben escribir programas que funcionan en un nivel de granularidad más fino que los elementos y los atributos.</span><span class="sxs-lookup"><span data-stu-id="25e87-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="25e87-104">A menudo deben trabajar en el nivel del nodo, manipulando nodos de texto, procesando instrucciones y comentarios.</span><span class="sxs-lookup"><span data-stu-id="25e87-104">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="25e87-105">En este tema se proporcionan algunos detalles acerca de la programación en el nivel del nodo.</span><span class="sxs-lookup"><span data-stu-id="25e87-105">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="25e87-106">Detalles del nodo</span><span class="sxs-lookup"><span data-stu-id="25e87-106">Node Details</span></span>  
 <span data-ttu-id="25e87-107">Existen varios detalles de programación que un programador que trabaja en el nivel de nodo debe conocer.</span><span class="sxs-lookup"><span data-stu-id="25e87-107">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="25e87-108">La propiedad primaria de los nodos secundarios de XDocument está establecida en NULL</span><span class="sxs-lookup"><span data-stu-id="25e87-108">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="25e87-109">La propiedad <xref:System.Xml.Linq.XObject.Parent%2A> contiene el <xref:System.Xml.Linq.XElement> primario, no el nodo primario.</span><span class="sxs-lookup"><span data-stu-id="25e87-109">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="25e87-110">Los nodos secundarios de <xref:System.Xml.Linq.XDocument> no tienen <xref:System.Xml.Linq.XElement> primario.</span><span class="sxs-lookup"><span data-stu-id="25e87-110">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="25e87-111">Su elemento primario es el documento, de forma que la propiedad <xref:System.Xml.Linq.XObject.Parent%2A> para esos nodos se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="25e87-111">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="25e87-112">En el siguiente ejemplo se muestra esto:</span><span class="sxs-lookup"><span data-stu-id="25e87-112">The following example demonstrates this:</span></span>  
  
```csharp  
XDocument doc = XDocument.Parse(@"<!-- a comment --><Root/>");  
Console.WriteLine(doc.Nodes().OfType<XComment>().First().Parent == null);  
Console.WriteLine(doc.Root.Parent == null);  
```  
  
 <span data-ttu-id="25e87-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="25e87-113">This example produces the following output:</span></span>  
  
```output  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="25e87-114">Los nodos de texto adyacentes son posibles</span><span class="sxs-lookup"><span data-stu-id="25e87-114">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="25e87-115">En varios modelos de programación XML, los nodos de texto adyacente siempre están combinados.</span><span class="sxs-lookup"><span data-stu-id="25e87-115">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="25e87-116">A veces se denomina normalización de los nodos de texto.</span><span class="sxs-lookup"><span data-stu-id="25e87-116">This is sometimes called normalization of text nodes.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="25e87-117">no normaliza nodos de texto.</span><span class="sxs-lookup"><span data-stu-id="25e87-117">does not normalize text nodes.</span></span> <span data-ttu-id="25e87-118">Si agrega dos nodos de texto al mismo elemento, tendrá como resultado nodos de texto adyacentes.</span><span class="sxs-lookup"><span data-stu-id="25e87-118">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="25e87-119">En cambio, si agrega contenido especificado como una cadena en lugar de un nodo <xref:System.Xml.Linq.XText>, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] puede combinar la cadena con un nodo de texto adyacente.</span><span class="sxs-lookup"><span data-stu-id="25e87-119">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="25e87-120">En el siguiente ejemplo se muestra esto:</span><span class="sxs-lookup"><span data-stu-id="25e87-120">The following example demonstrates this:</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does not add a new text node  
xmlTree.Add("new content");  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
  
// this does add a new, adjacent text node  
xmlTree.Add(new XText("more text"));  
Console.WriteLine(xmlTree.Nodes().OfType<XText>().Count());  
```  
  
 <span data-ttu-id="25e87-121">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="25e87-121">This example produces the following output:</span></span>  
  
```output  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="25e87-122">Los nodos de texto adyacentes vacíos son posibles</span><span class="sxs-lookup"><span data-stu-id="25e87-122">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="25e87-123">En algunos modelos de programación XML, se garantiza que los nodos de texto no contienen la cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="25e87-123">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="25e87-124">El razonamiento es que ese nodo de texto no tiene ninguna incidencia en la serialización de XML.</span><span class="sxs-lookup"><span data-stu-id="25e87-124">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="25e87-125">No obstante, por la misma razón que los nodos de texto adyacentes son posibles, si quita el texto de un nodo de texto estableciendo su valor en la cadena vacía, el nodo de texto en sí no se eliminará.</span><span class="sxs-lookup"><span data-stu-id="25e87-125">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```csharp  
XElement xmlTree = new XElement("Root", "Content");  
XText textNode = xmlTree.Nodes().OfType<XText>().First();  
  
// the following line does not cause the removal of the text node.  
textNode.Value = "";  
  
XText textNode2 = xmlTree.Nodes().OfType<XText>().First();  
Console.WriteLine(">>{0}<<", textNode2);
```  
  
 <span data-ttu-id="25e87-126">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="25e87-126">This example produces the following output:</span></span>  
  
```output  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="25e87-127">Un nodo de texto vacío incide sobre la serialización</span><span class="sxs-lookup"><span data-stu-id="25e87-127">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="25e87-128">Si un elemento contiene solamente un nodo de texto que está vacío, se serializa con la sintaxis de etiqueta larga: `<Child></Child>`.</span><span class="sxs-lookup"><span data-stu-id="25e87-128">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="25e87-129">Si un elemento no contiene ningún nodo secundario, se serializa con la sintaxis de etiqueta corta: `<Child />`.</span><span class="sxs-lookup"><span data-stu-id="25e87-129">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```csharp  
XElement child1 = new XElement("Child1",  
    new XText("")  
);  
XElement child2 = new XElement("Child2");  
Console.WriteLine(child1);  
Console.WriteLine(child2);
```  
  
 <span data-ttu-id="25e87-130">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="25e87-130">This example produces the following output:</span></span>  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="25e87-131">Los espacios de nombres son atributos en el árbol LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="25e87-131">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="25e87-132">Aunque las declaraciones del espacio de nombres tienen una sintaxis idéntica a los atributos, en algunas interfaces de programación como XSLT y XPath, las declaraciones de espacios de nombres no se consideran atributos.</span><span class="sxs-lookup"><span data-stu-id="25e87-132">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="25e87-133">No obstante, en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], los espacios de nombres se almacenan como objetos <xref:System.Xml.Linq.XAttribute> en el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="25e87-133">However, in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="25e87-134">Si recorre en iteración los atributos de un elemento que contiene una declaración de espacio de nombres, verá la declaración de espacio de nombres como uno de los elementos de la recopilación devuelta.</span><span class="sxs-lookup"><span data-stu-id="25e87-134">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="25e87-135">La propiedad <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> indica si un atributo es una declaración de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="25e87-135">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>");  
foreach (XAttribute att in root.Attributes())  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, att.IsNamespaceDeclaration);  
```  
  
 <span data-ttu-id="25e87-136">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="25e87-136">This example produces the following output:</span></span>  
  
```output  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="25e87-137">Los métodos del eje XPath no devuelven un espacio en blanco secundario de XDocument</span><span class="sxs-lookup"><span data-stu-id="25e87-137">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="25e87-138">permite nodos de texto secundarios de un <xref:System.Xml.Linq.XDocument> mientras los nodos de texto contengan solamente espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="25e87-138">allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="25e87-139">No obstante, el modelo de objetos de XPath no incluye el espacio en blanco como nodos secundarios de un documento, así que, cuando recorra en iteración los elementos secundarios de <xref:System.Xml.Linq.XDocument> con el eje <xref:System.Xml.Linq.XContainer.Nodes%2A>, se devolverán los nodos de texto de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="25e87-139">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white-space text nodes will be returned.</span></span> <span data-ttu-id="25e87-140">En cambio, cuando recorra en iteración los elementos secundarios de <xref:System.Xml.Linq.XDocument> con los métodos del eje de XPath, no se devolverán los nodos de texto de espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="25e87-140">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white-space text nodes will not be returned.</span></span>  
  
```csharp  
// Create a document with some white-space child nodes of the document.  
XDocument root = XDocument.Parse(  
@"<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
  
<Root/>  
  
<!--a comment-->  
", LoadOptions.PreserveWhitespace);  
  
// count the white-space child nodes using LINQ to XML  
Console.WriteLine(root.Nodes().OfType<XText>().Count());  
  
// count the white-space child nodes using XPathEvaluate  
Console.WriteLine(((IEnumerable)root.XPathEvaluate("text()")).OfType<XText>().Count());
```  
  
 <span data-ttu-id="25e87-141">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="25e87-141">This example produces the following output:</span></span>  
  
```output  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="25e87-142">Los objetos XDeclaration no son nodos</span><span class="sxs-lookup"><span data-stu-id="25e87-142">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="25e87-143">Cuando recorra en iteración los nodos secundarios de <xref:System.Xml.Linq.XDocument>, no verá el objeto de declaración XML.</span><span class="sxs-lookup"><span data-stu-id="25e87-143">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="25e87-144">Es una propiedad del documento, no un nodo secundario de él.</span><span class="sxs-lookup"><span data-stu-id="25e87-144">It is a property of the document, not a child node of it.</span></span>  
  
```csharp  
XDocument doc = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root")  
);  
doc.Save("Temp.xml");  
Console.WriteLine(File.ReadAllText("Temp.xml"));  
  
// this shows that there is only one child node of the document  
Console.WriteLine(doc.Nodes().Count());  
```  
  
 <span data-ttu-id="25e87-145">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="25e87-145">This example produces the following output:</span></span>  
  
```output  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  