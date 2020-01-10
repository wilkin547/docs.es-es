---
title: Espacios de nombres y consultas XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
ms.openlocfilehash: 91503ce0bffa1a9390432a51bff1ef10d80f563a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709782"
---
# <a name="xpath-queries-and-namespaces"></a><span data-ttu-id="74cd8-102">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="74cd8-102">XPath Queries and Namespaces</span></span>
<span data-ttu-id="74cd8-103">Las consultas XPath distinguen los espacios de nombres de un documento XML y pueden utilizar prefijos de espacio de nombres para calificar nombres de atributos y elementos.</span><span class="sxs-lookup"><span data-stu-id="74cd8-103">XPath queries are aware of namespaces in an XML document and can use namespace prefixes to qualify element and attribute names.</span></span> <span data-ttu-id="74cd8-104">Al calificar los nombres de atributos y elementos con un prefijo de espacio de nombres, se limitan los nodos que devuelve la consulta XPath a únicamente aquellos nodos que pertenecen a un espacio de nombres específico.</span><span class="sxs-lookup"><span data-stu-id="74cd8-104">Qualifying element and attribute names with a namespace prefix limits the nodes returned by an XPath query to only those nodes that belong to a specific namespace.</span></span>  
  
 <span data-ttu-id="74cd8-105">Por ejemplo, si el prefijo `books` se asigna al espacio de nombres `http://www.contoso.com/books`, la siguiente consulta XPath `/books:books/books:book` solo selecciona los elementos `book` en el espacio de nombres `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="74cd8-105">For example if the prefix `books` maps to the namespace `http://www.contoso.com/books`, then the following XPath query `/books:books/books:book` selects only those `book` elements in the namespace `http://www.contoso.com/books`.</span></span>  
  
## <a name="the-xmlnamespacemanager"></a><span data-ttu-id="74cd8-106">XmlNamespaceManager</span><span class="sxs-lookup"><span data-stu-id="74cd8-106">The XmlNamespaceManager</span></span>  
 <span data-ttu-id="74cd8-107">Para utilizar espacios de nombres en una consulta XPath, se crea un objeto derivado de la interfaz <xref:System.Xml.IXmlNamespaceResolver> como la clase <xref:System.Xml.XmlNamespaceManager> con el prefijo e identificador URI de espacio de nombres para incluirlo en la consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="74cd8-107">To use namespaces in an XPath query, an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface like the <xref:System.Xml.XmlNamespaceManager> class is constructed with the namespace URI and prefix to include in the XPath query.</span></span>  
  
 <span data-ttu-id="74cd8-108">El objeto <xref:System.Xml.XmlNamespaceManager> se puede utilizar en la consulta en cada una de las siguientes formas.</span><span class="sxs-lookup"><span data-stu-id="74cd8-108">The <xref:System.Xml.XmlNamespaceManager> object may be used in the query in each of the following ways.</span></span>  
  
- <span data-ttu-id="74cd8-109">El objeto <xref:System.Xml.XmlNamespaceManager> se asocia a un objeto <xref:System.Xml.XPath.XPathExpression> existente utilizando el método <xref:System.Xml.XPath.XPathExpression.SetContext%2A> del objeto <xref:System.Xml.XPath.XPathExpression>.</span><span class="sxs-lookup"><span data-stu-id="74cd8-109">The <xref:System.Xml.XmlNamespaceManager> object is associated with an existing <xref:System.Xml.XPath.XPathExpression> object by using the <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method of the <xref:System.Xml.XPath.XPathExpression> object.</span></span> <span data-ttu-id="74cd8-110">También se puede compilar un nuevo objeto <xref:System.Xml.XPath.XPathExpression> utilizando el método <xref:System.Xml.XPath.XPathExpression.Compile%2A> estático que toma una cadena que representa la expresión XPath y un objeto <xref:System.Xml.XmlNamespaceManager> como parámetros y devuelve un nuevo objeto <xref:System.Xml.XPath.XPathExpression>.</span><span class="sxs-lookup"><span data-stu-id="74cd8-110">You may also compile a new <xref:System.Xml.XPath.XPathExpression> object using the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method which takes a string representing the XPath expression and an <xref:System.Xml.XmlNamespaceManager> object as parameters and returns a new <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
- <span data-ttu-id="74cd8-111">El propio objeto <xref:System.Xml.XmlNamespaceManager> se pasa como parámetro a un método de la clase <xref:System.Xml.XPath.XPathNavigator> de aceptación junto con una cadena que representa la expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="74cd8-111">The <xref:System.Xml.XmlNamespaceManager> object itself is passed as a parameter to an accepting <xref:System.Xml.XPath.XPathNavigator> class method along with a string representing the XPath expression.</span></span>  
  
 <span data-ttu-id="74cd8-112">A continuación se enumeran los métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que aceptan un objeto derivado de la interfaz <xref:System.Xml.IXmlNamespaceResolver> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="74cd8-112">The following are the methods of the <xref:System.Xml.XPath.XPathNavigator> class that accept an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface as a parameter.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a><span data-ttu-id="74cd8-113">Espacio de nombres predeterminado</span><span class="sxs-lookup"><span data-stu-id="74cd8-113">The Default Namespace</span></span>  
 <span data-ttu-id="74cd8-114">En el siguiente documento XML, se utiliza el espacio de nombres predeterminado con un prefijo vacío para declarar el espacio de nombres `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="74cd8-114">In the XML document that follows, the default namespace with an empty prefix is used to declare the `http://www.contoso.com/books` namespace.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="74cd8-115">XPath trata el prefijo vacío como el espacio de nombres `null`.</span><span class="sxs-lookup"><span data-stu-id="74cd8-115">XPath treats the empty prefix as the `null` namespace.</span></span> <span data-ttu-id="74cd8-116">Dicho de otro modo, en las consultas XPath solo se pueden utilizar prefijos asignados a espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="74cd8-116">In other words, only prefixes mapped to namespaces can be used in XPath queries.</span></span> <span data-ttu-id="74cd8-117">Esto significa que si desea realizar una consulta en un espacio de nombres de un documento XML, aunque se trate del espacio de nombres predeterminado, tiene que definir un prefijo para él.</span><span class="sxs-lookup"><span data-stu-id="74cd8-117">This means that if you want to query against a namespace in an XML document, even if it is the default namespace, you need to define a prefix for it.</span></span>  
  
 <span data-ttu-id="74cd8-118">Por ejemplo, si no se define un prefijo para el documento XML anterior, la consulta XPath `/books/book` no devolvería ningún resultado.</span><span class="sxs-lookup"><span data-stu-id="74cd8-118">For example, without defining a prefix for the XML document above, the XPath query `/books/book` would not return any results.</span></span>  
  
 <span data-ttu-id="74cd8-119">Se debe utilizar un prefijo para evitar ambigüedades al consultar documentos que tienen algunos nodos que no están en un espacio de nombres y otros que están en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="74cd8-119">A prefix must be bound to prevent ambiguity when querying documents with some nodes not in a namespace, and some in a default namespace.</span></span>  
  
 <span data-ttu-id="74cd8-120">En el siguiente código se define un prefijo para el espacio de nombres predeterminado y se seleccionan todos los elementos `book` del espacio de nombres `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="74cd8-120">The following code defines a prefix for the default namespace and selects all the `book` elements from the `http://www.contoso.com/books` namespace.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a><span data-ttu-id="74cd8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="74cd8-121">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="74cd8-122">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="74cd8-122">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="74cd8-123">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="74cd8-123">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="74cd8-124">Evaluación de expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="74cd8-124">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="74cd8-125">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="74cd8-125">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="74cd8-126">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="74cd8-126">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="74cd8-127">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="74cd8-127">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
