---
title: Modificar elementos, atributos y nodos en un Tree1 XML
ms.date: 07/20/2015
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
ms.openlocfilehash: c3863f52976303407cbad3d0bacc9bd0b2ec1d31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547545"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="4bb3c-102">Modificar elementos, atributos y nodos de un árbol XML</span><span class="sxs-lookup"><span data-stu-id="4bb3c-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="4bb3c-103">La tabla siguiente resume los métodos y las propiedades que puede usar para modificar un elemento, sus elementos secundarios o sus atributos.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="4bb3c-104">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="4bb3c-105">Método</span><span class="sxs-lookup"><span data-stu-id="4bb3c-105">Method</span></span>|<span data-ttu-id="4bb3c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bb3c-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-107">Reemplaza un elemento por XML analizado.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-108">Quita todo el contenido (atributos y nodos secundarios) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-109">Quita los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-110">Reemplaza todo el contenido (nodos secundarios y atributos) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-111">Reemplaza los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-112">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-112">Sets the value of an attribute.</span></span> <span data-ttu-id="4bb3c-113">Crea el atributo si no existe.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="4bb3c-114">Si el valor se establece en `null`, quita el atributo.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-115">Establece el valor de un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-115">Sets the value of a child element.</span></span> <span data-ttu-id="4bb3c-116">Crea el elemento si no existe.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="4bb3c-117">Si el valor se establece en `null`, quita el elemento.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-118">Reemplaza el contenido (nodos secundarios) de un elemento por el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-119">Establece el valor de un elemento.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="4bb3c-120">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="4bb3c-121">Método</span><span class="sxs-lookup"><span data-stu-id="4bb3c-121">Method</span></span>|<span data-ttu-id="4bb3c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bb3c-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-123">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-124">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="4bb3c-125">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XNode> (incluyendo <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="4bb3c-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="4bb3c-126">Método</span><span class="sxs-lookup"><span data-stu-id="4bb3c-126">Method</span></span>|<span data-ttu-id="4bb3c-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bb3c-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-128">Reemplaza un nodo por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="4bb3c-129">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="4bb3c-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="4bb3c-130">Método</span><span class="sxs-lookup"><span data-stu-id="4bb3c-130">Method</span></span>|<span data-ttu-id="4bb3c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bb3c-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="4bb3c-132">Reemplaza los nodos secundarios por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="4bb3c-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bb3c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bb3c-133">See also</span></span>
- [<span data-ttu-id="4bb3c-134">Modificar árboles XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bb3c-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
