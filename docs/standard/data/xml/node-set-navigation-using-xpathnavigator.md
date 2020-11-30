---
title: Navegación por un conjunto de nodos con XPathNavigator
ms.date: 03/30/2017
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
ms.openlocfilehash: 592acfb5e4065d707f4dda09f349e8b783656148
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714307"
---
# <a name="node-set-navigation-using-xpathnavigator"></a><span data-ttu-id="569aa-102">Navegación por un conjunto de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="569aa-102">Node Set Navigation Using XPathNavigator</span></span>

<span data-ttu-id="569aa-103">Para navegar por los nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>, utilice los métodos de navegación por conjuntos de nodos de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="569aa-103">You can navigate over nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="569aa-104">Puede navegar por todos los nodos o por un conjunto seleccionado de nodos que devuelve uno de los métodos de selección de la clase <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="569aa-104">You can navigate over all the nodes or over a selected set of nodes returned by one of the selection methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="element-node-set-navigation"></a><span data-ttu-id="569aa-105">Navegación por conjuntos de nodos de elementos</span><span class="sxs-lookup"><span data-stu-id="569aa-105">Element Node Set Navigation</span></span>  

 <span data-ttu-id="569aa-106">La clase <xref:System.Xml.XPath.XPathNavigator> incluye varios métodos que sirven para navegar por nodos de elementos.</span><span class="sxs-lookup"><span data-stu-id="569aa-106">The <xref:System.Xml.XPath.XPathNavigator> class provides several methods used to navigate element nodes.</span></span> <span data-ttu-id="569aa-107">En la siguiente tabla se muestran los métodos de navegación disponibles y una descripción de su forma de moverse; no se incluyen los métodos que sirven para navegar por los nodos de espacios de nombres y atributos.</span><span class="sxs-lookup"><span data-stu-id="569aa-107">The following table shows the navigation methods available and a description of how they move; this does not include methods used to navigate attribute and namespace nodes.</span></span>  
  
 <span data-ttu-id="569aa-108">Para más información sobre la selección de nodos en un objeto <xref:System.Xml.XPath.XPathNavigator>, vea [Selección, evaluación y coincidencia de datos XML con XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="569aa-108">For more information about selecting nodes in an <xref:System.Xml.XPath.XPathNavigator> object, see [Selecting, Evaluating and Matching XML Data using XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span></span> <span data-ttu-id="569aa-109">Para más información sobre la navegación por los nodos de atributo y espacio de nombres, vea [Navegación por nodos de espacios de nombres y atributos con XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="569aa-109">For more information about navigating attribute and namespace nodes, see [Attribute and Namespace Node Navigation Using XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span></span>  
  
|<span data-ttu-id="569aa-110">Método</span><span class="sxs-lookup"><span data-stu-id="569aa-110">Method</span></span>|<span data-ttu-id="569aa-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="569aa-111">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|<span data-ttu-id="569aa-112">Mueve <xref:System.Xml.XPath.XPathNavigator> a la misma posición del <xref:System.Xml.XPath.XPathNavigator> especificado.</span><span class="sxs-lookup"><span data-stu-id="569aa-112">Moves the <xref:System.Xml.XPath.XPathNavigator> to the same position of the <xref:System.Xml.XPath.XPathNavigator> specified.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|<span data-ttu-id="569aa-113">Mueve <xref:System.Xml.XPath.XPathNavigator> a un nodo secundario del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="569aa-113">Moves the <xref:System.Xml.XPath.XPathNavigator> to a child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|<span data-ttu-id="569aa-114">Mueve <xref:System.Xml.XPath.XPathNavigator> al primer nodo relacionado del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="569aa-114">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|<span data-ttu-id="569aa-115">Mueve <xref:System.Xml.XPath.XPathNavigator> al primer nodo secundario del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="569aa-115">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|<span data-ttu-id="569aa-116">Mueve <xref:System.Xml.XPath.XPathNavigator> al elemento especificado en el orden del documento.</span><span class="sxs-lookup"><span data-stu-id="569aa-116">Moves the <xref:System.Xml.XPath.XPathNavigator> to the specified element in document order.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|<span data-ttu-id="569aa-117">Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo que tiene un atributo del tipo `ID` con un valor que coincide con la <xref:System.String> especificada.</span><span class="sxs-lookup"><span data-stu-id="569aa-117">Moves the <xref:System.Xml.XPath.XPathNavigator> to the node that has an attribute of type `ID` with a value that matches the given <xref:System.String>.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|<span data-ttu-id="569aa-118">Mueve <xref:System.Xml.XPath.XPathNavigator> al siguiente nodo relacionado del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="569aa-118">Moves the <xref:System.Xml.XPath.XPathNavigator> to the next sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|<span data-ttu-id="569aa-119">Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo principal del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="569aa-119">Moves the <xref:System.Xml.XPath.XPathNavigator> to the parent node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|<span data-ttu-id="569aa-120">Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo relacionado anterior del nodo actual.</span><span class="sxs-lookup"><span data-stu-id="569aa-120">Moves the <xref:System.Xml.XPath.XPathNavigator> to the previous sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|<span data-ttu-id="569aa-121">Mueve <xref:System.Xml.XPath.XPathNavigator> al nodo raíz del documento XML.</span><span class="sxs-lookup"><span data-stu-id="569aa-121">Moves the <xref:System.Xml.XPath.XPathNavigator> to the root node of the XML document.</span></span>|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a><span data-ttu-id="569aa-122">Navegación por nodos de instrucción de procesamiento y comentarios</span><span class="sxs-lookup"><span data-stu-id="569aa-122">Comments and Processing Instruction Node Navigation</span></span>  

 <span data-ttu-id="569aa-123">Los siguientes métodos de la clase <xref:System.Xml.XPath.XPathNavigator> sirven para navegar a comentarios o instrucciones de procesamiento desde otros nodos de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="569aa-123">The following <xref:System.Xml.XPath.XPathNavigator> class methods are valid for moving to comments or processing instructions from other nodes in an XML document.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a><span data-ttu-id="569aa-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="569aa-124">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="569aa-125">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="569aa-125">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="569aa-126">Navegación por nodos de espacios de nombres y atributos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="569aa-126">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="569aa-127">Extracción de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="569aa-127">Extract XML Data Using XPathNavigator</span></span>](extract-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="569aa-128">Acceso a datos XML fuertemente tipados utilizando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="569aa-128">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
