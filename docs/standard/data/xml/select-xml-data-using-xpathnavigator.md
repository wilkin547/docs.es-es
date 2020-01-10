---
title: Seleccionar datos XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: c268c49e-32b9-4171-b782-dcb7b065fa73
ms.openlocfilehash: 99b6b3b6959abf4c8adc313364ad641249bd9bc3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710172"
---
# <a name="select-xml-data-using-xpathnavigator"></a><span data-ttu-id="b3a38-102">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b3a38-102">Select XML Data Using XPathNavigator</span></span>
<span data-ttu-id="b3a38-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para seleccionar un conjunto de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> utilizando una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="b3a38-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="b3a38-104">Una vez seleccionado, puede iterar por el conjunto de nodos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b3a38-104">Once selected, you can iterate over the selected set of nodes.</span></span>  
  
## <a name="xpathnavigator-selection-methods"></a><span data-ttu-id="b3a38-105">Métodos de selección de XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b3a38-105">XPathNavigator Selection Methods</span></span>  
 <span data-ttu-id="b3a38-106">La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para seleccionar un conjunto de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> utilizando una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="b3a38-106">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="b3a38-107">La clase <xref:System.Xml.XPath.XPathNavigator> también incluye un conjunto de métodos optimizados para seleccionar nodos antecesores, secundarios y descendientes más rápido que con una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="b3a38-107">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of optimized methods for selecting ancestor, child and descendant nodes faster than using an XPath expression.</span></span> <span data-ttu-id="b3a38-108">El conjunto seleccionado de nodos se devuelve en un objeto <xref:System.Xml.XPath.XPathNodeIterator> o un objeto <xref:System.Xml.XPath.XPathNavigator> en el caso de haya un solo nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b3a38-108">The selected set of nodes is returned in an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
### <a name="selecting-nodes-using-xpath-expressions"></a><span data-ttu-id="b3a38-109">Selección de nodos con expresiones XPath</span><span class="sxs-lookup"><span data-stu-id="b3a38-109">Selecting Nodes Using XPath Expressions</span></span>  
 <span data-ttu-id="b3a38-110">Para seleccionar un conjunto de nodos con una expresión XPath, utilice uno de los siguientes métodos de selección.</span><span class="sxs-lookup"><span data-stu-id="b3a38-110">To select a set of nodes using an XPath expression, use one of the following selection methods.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="b3a38-111">Cuando se llama a estos métodos, éstos devuelven un conjunto de nodos por los que puede navegar libremente utilizando un objeto <xref:System.Xml.XPath.XPathNodeIterator> o un objeto <xref:System.Xml.XPath.XPathNavigator> en el caso de que haya un solo nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b3a38-111">When called, these methods return a set of nodes that you can navigate freely using an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
 <span data-ttu-id="b3a38-112">La navegación por un objeto <xref:System.Xml.XPath.XPathNodeIterator> no afecta a la posición del objeto <xref:System.Xml.XPath.XPathNavigator> que se ha utilizado para crearlo.</span><span class="sxs-lookup"><span data-stu-id="b3a38-112">Navigating with an <xref:System.Xml.XPath.XPathNodeIterator> object does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span> <span data-ttu-id="b3a38-113">El objeto <xref:System.Xml.XPath.XPathNavigator> que devuelven los métodos <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> se sitúa en el único nodo devuelto y tampoco afecta a la posición del objeto <xref:System.Xml.XPath.XPathNavigator> que se ha utilizado para crearlo.</span><span class="sxs-lookup"><span data-stu-id="b3a38-113">The <xref:System.Xml.XPath.XPathNavigator> object returned from the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> methods is positioned on the single returned node and also does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span>  
  
 <span data-ttu-id="b3a38-114">En el siguiente ejemplo, se muestra la creación de un objeto <xref:System.Xml.XPath.XPathNavigator> a partir de un objeto <xref:System.Xml.XPath.XPathDocument>, el uso del método <xref:System.Xml.XPath.XPathNavigator.Select%2A> para seleccionar nodos en el objeto <xref:System.Xml.XPath.XPathDocument> y el uso del objeto <xref:System.Xml.XPath.XPathNodeIterator> para iterar por los nodos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="b3a38-114">The following example shows the creation of an <xref:System.Xml.XPath.XPathNavigator> object from an <xref:System.Xml.XPath.XPathDocument> object, the use of the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method to select nodes in the <xref:System.Xml.XPath.XPathDocument> object, and the use of the <xref:System.Xml.XPath.XPathNodeIterator> object to iterate over the selected nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim nodes As XPathNodeIterator = navigator.Select("/bookstore/book")  
  
While nodes.MoveNext()  
    Console.WriteLine(nodes.Current.Name)  
End While  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathNodeIterator nodes = navigator.Select("/bookstore/book");  
  
while(nodes.MoveNext())  
{  
    Console.WriteLine(nodes.Current.Name);  
}  
```  
  
 <span data-ttu-id="b3a38-115">En el ejemplo se toma como entrada el archivo `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="b3a38-115">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="optimized-selection-methods"></a><span data-ttu-id="b3a38-116">Métodos de selección optimizados</span><span class="sxs-lookup"><span data-stu-id="b3a38-116">Optimized Selection Methods</span></span>  
 <span data-ttu-id="b3a38-117">Los métodos <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> y <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> representan expresiones XPath que se utilizan habitualmente para recuperar nodos secundarios, descendientes y antecesores.</span><span class="sxs-lookup"><span data-stu-id="b3a38-117">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class represent XPath expressions commonly used to retrieve child, descendant, and ancestor nodes.</span></span> <span data-ttu-id="b3a38-118">Estos métodos tienen optimizado su rendimiento y son más rápidos que sus expresiones XPath correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b3a38-118">These methods are optimized for performance and are faster than their corresponding XPath expressions.</span></span> <span data-ttu-id="b3a38-119">Los métodos <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> y <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> seleccionan nodos antecesores, secundarios y descendientes basándose en un valor <xref:System.Xml.XPath.XPathNodeType> o el nombre local e identificador URI de espacio de nombres de los nodos que se van a seleccionar.</span><span class="sxs-lookup"><span data-stu-id="b3a38-119">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods selects ancestor, child, and descendant nodes based on an <xref:System.Xml.XPath.XPathNodeType> value or the local name and namespace URI of the nodes to select.</span></span> <span data-ttu-id="b3a38-120">Los nodos antecesores, secundarios y descendientes se devuelven en un objeto <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="b3a38-120">The selected ancestor, child, and descendant nodes are returned in an <xref:System.Xml.XPath.XPathNodeIterator> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a38-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3a38-121">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="b3a38-122">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="b3a38-122">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="b3a38-123">Evaluación de expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b3a38-123">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="b3a38-124">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b3a38-124">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="b3a38-125">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="b3a38-125">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="b3a38-126">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="b3a38-126">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="b3a38-127">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="b3a38-127">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
