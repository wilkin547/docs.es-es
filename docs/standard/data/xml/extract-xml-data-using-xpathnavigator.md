---
title: Extraer datos XML con XPathNavigator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c42539db3750ebc2a4220ef776b89bbabe6aaca3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="extract-xml-data-using-xpathnavigator"></a><span data-ttu-id="a1948-102">Extraer datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a1948-102">Extract XML Data Using XPathNavigator</span></span>
<span data-ttu-id="a1948-103">Existen varias formas de representar un documento XML en Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a1948-103">There are several different ways to represent an XML document in the Microsoft .NET Framework.</span></span> <span data-ttu-id="a1948-104">Entre ellas se incluye el uso de <xref:System.String> o de las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument> o <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="a1948-104">This includes using a <xref:System.String>, or by using the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument>, or <xref:System.Xml.XPath.XPathDocument> classes.</span></span> <span data-ttu-id="a1948-105">Para que sea más fácil moverse entre estas diferentes representaciones de un documento XML, la clase <xref:System.Xml.XPath.XPathNavigator> incluye una serie de métodos y propiedades para extraer el código XML como un objeto <xref:System.String>, <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="a1948-105">To facilitate moving between these different representations of an XML document, the <xref:System.Xml.XPath.XPathNavigator> class provides a number of methods and properties for extracting the XML as a <xref:System.String>, <xref:System.Xml.XmlReader> object or <xref:System.Xml.XmlWriter> object.</span></span>  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a><span data-ttu-id="a1948-106">Conversión de XPathNavigator en una cadena</span><span class="sxs-lookup"><span data-stu-id="a1948-106">Convert an XPathNavigator to a String</span></span>  
 <span data-ttu-id="a1948-107">La propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> se utiliza para obtener el marcado de todo el documento XML o tan sólo el de un nodo y sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a1948-107">The <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class is used to get the markup of the entire XML document or just the markup of a single node and its child nodes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1948-108">La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> obtiene solamente el marcado de los nodos secundarios de un nodo.</span><span class="sxs-lookup"><span data-stu-id="a1948-108">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property gets the markup of just the child nodes of a node.</span></span>  
  
 <span data-ttu-id="a1948-109">El siguiente código muestra cómo guardar todo un documento XML contenido en un objeto <xref:System.Xml.XPath.XPathNavigator> como <xref:System.String>, así como un solo nodo y sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a1948-109">The following code example shows how to save an entire XML document contained in an <xref:System.Xml.XPath.XPathNavigator> object as a <xref:System.String>, as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a><span data-ttu-id="a1948-110">Conversión de XPathNavigator en XmlReader</span><span class="sxs-lookup"><span data-stu-id="a1948-110">Convert an XPathNavigator to an XmlReader</span></span>  
 <span data-ttu-id="a1948-111">El método <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> se utiliza para secuenciar todo el contenido de un documento XML o tan sólo un nodo y sus nodos secundarios en un objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a1948-111">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlReader> object.</span></span>  
  
 <span data-ttu-id="a1948-112">Cuando se crea el objeto <xref:System.Xml.XmlReader> con el nodo actual y sus nodos secundarios, la propiedad <xref:System.Xml.XmlReader> del objeto <xref:System.Xml.XmlReader.ReadState%2A> se establece en <xref:System.Xml.ReadState.Initial>.</span><span class="sxs-lookup"><span data-stu-id="a1948-112">When the <xref:System.Xml.XmlReader> object is created with the current node and its child nodes, the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.Initial>.</span></span> <span data-ttu-id="a1948-113">Cuando por primera vez se llama al método <xref:System.Xml.XmlReader> del objeto <xref:System.Xml.XmlReader.Read%2A>, <xref:System.Xml.XmlReader> se desplaza al nodo actual de <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a1948-113">When the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.Read%2A> method is called for the first time, the <xref:System.Xml.XmlReader> is moved to the current node of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="a1948-114">El nuevo objeto <xref:System.Xml.XmlReader> continúa leyendo hasta llegar al final del árbol de XML.</span><span class="sxs-lookup"><span data-stu-id="a1948-114">The new <xref:System.Xml.XmlReader> object continues to read until the end of the XML tree is reached.</span></span> <span data-ttu-id="a1948-115">En este punto, el método <xref:System.Xml.XmlReader.Read%2A> devuelve `false` y la propiedad <xref:System.Xml.XmlReader> del objeto <xref:System.Xml.XmlReader.ReadState%2A> se establece en <xref:System.Xml.ReadState.EndOfFile>.</span><span class="sxs-lookup"><span data-stu-id="a1948-115">At this point, the <xref:System.Xml.XmlReader.Read%2A> method returns `false` and the <xref:System.Xml.XmlReader> object's <xref:System.Xml.XmlReader.ReadState%2A> property is set to <xref:System.Xml.ReadState.EndOfFile>.</span></span>  
  
 <span data-ttu-id="a1948-116">La posición del objeto <xref:System.Xml.XPath.XPathNavigator> no cambia debido a la creación o el movimiento del objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="a1948-116">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation or movement of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="a1948-117">El método <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> sólo es válido cuando se encuentra situado en un elemento o en un nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="a1948-117">The <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> method is only valid when positioned on an element or root node.</span></span>  
  
 <span data-ttu-id="a1948-118">En el siguiente ejemplo se muestra cómo obtener un objeto <xref:System.Xml.XmlReader> que contiene todo el documento XML de un objeto <xref:System.Xml.XPath.XPathDocument>, así como un solo nodo y sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a1948-118">The following example shows how to get an <xref:System.Xml.XmlReader> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 <span data-ttu-id="a1948-119">En el ejemplo se toma como entrada el archivo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="a1948-119">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a><span data-ttu-id="a1948-120">Conversión de XPathNavigator en XmlWriter</span><span class="sxs-lookup"><span data-stu-id="a1948-120">Converting an XPathNavigator to an XmlWriter</span></span>  
 <span data-ttu-id="a1948-121">El método <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> se utiliza para secuenciar todo el contenido de un documento XML o tan sólo un nodo y sus nodos secundarios en un objeto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="a1948-121">The <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> method is used to stream the entire contents of an XML document or just a single node and its child nodes to an <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="a1948-122">La posición del objeto <xref:System.Xml.XPath.XPathNavigator> no cambia debido a la creación del objeto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="a1948-122">The <xref:System.Xml.XPath.XPathNavigator> object's position is unchanged by the creation of the <xref:System.Xml.XmlWriter> object.</span></span>  
  
 <span data-ttu-id="a1948-123">En el siguiente ejemplo se muestra cómo obtener un objeto <xref:System.Xml.XmlWriter> que contiene todo el documento XML de un objeto <xref:System.Xml.XPath.XPathDocument>, así como un solo nodo y sus nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a1948-123">The following example shows how to get an <xref:System.Xml.XmlWriter> object containing the entire XML document in an <xref:System.Xml.XPath.XPathDocument> object as well as a single node and its child nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 <span data-ttu-id="a1948-124">El ejemplo toma como entrada el archivo `books.xml` que aparecía anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a1948-124">The example takes the `books.xml` file found earlier in this topic as input.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1948-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1948-125">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="a1948-126">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="a1948-126">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="a1948-127">Navegación de conjunto de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a1948-127">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="a1948-128">Atributo y navegación Namespace nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a1948-128">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="a1948-129">Acceso a fuertemente tipados datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a1948-129">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
