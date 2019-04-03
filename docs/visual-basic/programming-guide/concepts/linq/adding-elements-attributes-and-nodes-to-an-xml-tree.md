---
title: Agregar elementos, atributos y nodos a un árbol XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
ms.openlocfilehash: 35d3bdb27342dd7a871778ad4749db4d6849bd60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814323"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a><span data-ttu-id="9e785-102">Agregar elementos, atributos y nodos a un árbol XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e785-102">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="9e785-103">Puede agregar contenidos (elementos, atributos, comentarios, instrucciones de procesamiento, texto y bloques CDATA) a un árbol XML existente.</span><span class="sxs-lookup"><span data-stu-id="9e785-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="9e785-104">Métodos para agregar contenidos</span><span class="sxs-lookup"><span data-stu-id="9e785-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="9e785-105">Los métodos siguientes agregan contenidos secundarios a un <xref:System.Xml.Linq.XElement> o a un <xref:System.Xml.Linq.XDocument>:</span><span class="sxs-lookup"><span data-stu-id="9e785-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="9e785-106">Método</span><span class="sxs-lookup"><span data-stu-id="9e785-106">Method</span></span>|<span data-ttu-id="9e785-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e785-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="9e785-108">Agrega un contenido al final de los contenidos secundarios del <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="9e785-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="9e785-109">Agrega un contenido al comienzo de los contenidos secundarios del <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="9e785-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="9e785-110">Los métodos siguientes agregan contenidos como nodos relacionados de un <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="9e785-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="9e785-111">El nodo al que se agregan habitualmente contenidos relacionados es <xref:System.Xml.Linq.XElement>, aunque es posible agregar contenidos relacionados válidos a otros tipos de nodos, como por ejemplo, al nodo <xref:System.Xml.Linq.XText> o al nodo <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="9e785-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="9e785-112">Método</span><span class="sxs-lookup"><span data-stu-id="9e785-112">Method</span></span>|<span data-ttu-id="9e785-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e785-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="9e785-114">Añade un contenido detrás de <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="9e785-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="9e785-115">Agrega contenido antes de <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="9e785-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9e785-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e785-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9e785-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e785-117">Description</span></span>  
 <span data-ttu-id="9e785-118">El siguiente ejemplo crear dos árboles XML y, a continuación, modifica uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9e785-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9e785-119">Código</span><span class="sxs-lookup"><span data-stu-id="9e785-119">Code</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
```  
  
### <a name="comments"></a><span data-ttu-id="9e785-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e785-120">Comments</span></span>  
 <span data-ttu-id="9e785-121">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9e785-121">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e785-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e785-122">See also</span></span>

- [<span data-ttu-id="9e785-123">Modificar árboles XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e785-123">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
