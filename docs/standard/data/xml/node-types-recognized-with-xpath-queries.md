---
title: Tipos de nodos reconocidos con consultas XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
ms.openlocfilehash: cc1aa668ccf6fc7f210f48a28cf76b364459c784
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710549"
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="c5c07-102">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="c5c07-102">Node Types Recognized with XPath Queries</span></span>
<span data-ttu-id="c5c07-103">Los tipos de nodos que se reconocen en una consulta XPath no son los mismos que se encuentran en el Modelo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="c5c07-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="c5c07-104">Tipos de nodos XPath del W3C</span><span class="sxs-lookup"><span data-stu-id="c5c07-104">W3C XPath Node Types</span></span>  
 <span data-ttu-id="c5c07-105">Los tipos de nodos que se reconocen en una consulta XPath no son los tipos de nodos que se encuentran en el Modelo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="c5c07-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="c5c07-106">A continuación se enumeran los tipos de nodos XPath representados por la enumeración <xref:System.Xml.XPath.XPathNodeType>.</span><span class="sxs-lookup"><span data-stu-id="c5c07-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
- <xref:System.Xml.XPath.XPathNodeType.All>  
  
- <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
- <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
- <xref:System.Xml.XPath.XPathNodeType.Element>  
  
- <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
- <xref:System.Xml.XPath.XPathNodeType.Root>  
  
- <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.Text>  
  
- <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 <span data-ttu-id="c5c07-107">Estos tipos de nodos se basan en el modelo de datos XPath, donde los nodos se derivan del conjunto de información XML.</span><span class="sxs-lookup"><span data-stu-id="c5c07-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="c5c07-108">Los tipos de nodos <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> y <xref:System.Xml.XPath.XPathNodeType.Whitespace> son extensiones de Microsoft .NET Framework para los tipos de nodos básicos que se describen en el modelo de datos XPath.</span><span class="sxs-lookup"><span data-stu-id="c5c07-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="c5c07-109">El tipo de nodo de atributos se utiliza de manera diferente en el modelo de datos XPath y en el DOM.</span><span class="sxs-lookup"><span data-stu-id="c5c07-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="c5c07-110">En el modelo de datos XPath, el nodo de elementos tiene un conjunto de nodos de atributos relacionados con él y el nodo de elementos es el nodo principal de cada nodo de atributos.</span><span class="sxs-lookup"><span data-stu-id="c5c07-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="c5c07-111">Sin embargo, en el DOM, el nodo de elementos es el propietario y no el nodo principal.</span><span class="sxs-lookup"><span data-stu-id="c5c07-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="c5c07-112">En ambos modelos, los nodos de espacios de nombres y atributos no se consideran nodos secundarios del nodo de elementos.</span><span class="sxs-lookup"><span data-stu-id="c5c07-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="c5c07-113">El tipo de nodo de espacios de nombres es una adición al modelo de datos XPath y no es un tipo de nodo DOM reconocido.</span><span class="sxs-lookup"><span data-stu-id="c5c07-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="c5c07-114">Para más información sobre la navegación por los nodos de elemento, atributo y espacio de nombres, vea los temas [Navegación por un conjunto de nodos con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) y [Navegación por nodos de espacios de nombres y atributos con XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="c5c07-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c07-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5c07-115">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="c5c07-116">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="c5c07-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="c5c07-117">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c5c07-117">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="c5c07-118">Evaluación de expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c5c07-118">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="c5c07-119">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c5c07-119">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="c5c07-120">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="c5c07-120">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="c5c07-121">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="c5c07-121">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
