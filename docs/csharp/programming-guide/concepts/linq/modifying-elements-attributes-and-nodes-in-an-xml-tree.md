---
title: Modificar elementos, atributos y nodos de un árbol XML
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: a03045c9a4b7b0fb24bbe5c25211b9626cab9185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321274"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="b853e-102">Modificar elementos, atributos y nodos de un árbol XML</span><span class="sxs-lookup"><span data-stu-id="b853e-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="b853e-103">La tabla siguiente resume los métodos y las propiedades que puede usar para modificar un elemento, sus elementos secundarios o sus atributos.</span><span class="sxs-lookup"><span data-stu-id="b853e-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="b853e-104">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b853e-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="b853e-105">Método</span><span class="sxs-lookup"><span data-stu-id="b853e-105">Method</span></span>|<span data-ttu-id="b853e-106">Description</span><span class="sxs-lookup"><span data-stu-id="b853e-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-107">Reemplaza un elemento por XML analizado.</span><span class="sxs-lookup"><span data-stu-id="b853e-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-108">Quita todo el contenido (atributos y nodos secundarios) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b853e-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-109">Quita los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b853e-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-110">Reemplaza todo el contenido (nodos secundarios y atributos) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b853e-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-111">Reemplaza los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b853e-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-112">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="b853e-112">Sets the value of an attribute.</span></span> <span data-ttu-id="b853e-113">Crea el atributo si no existe.</span><span class="sxs-lookup"><span data-stu-id="b853e-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="b853e-114">Si el valor se establece en `null`, quita el atributo.</span><span class="sxs-lookup"><span data-stu-id="b853e-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-115">Establece el valor de un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="b853e-115">Sets the value of a child element.</span></span> <span data-ttu-id="b853e-116">Crea el elemento si no existe.</span><span class="sxs-lookup"><span data-stu-id="b853e-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="b853e-117">Si el valor se establece en `null`, quita el elemento.</span><span class="sxs-lookup"><span data-stu-id="b853e-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-118">Reemplaza el contenido (nodos secundarios) de un elemento por el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="b853e-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-119">Establece el valor de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b853e-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="b853e-120">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b853e-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="b853e-121">Método</span><span class="sxs-lookup"><span data-stu-id="b853e-121">Method</span></span>|<span data-ttu-id="b853e-122">Description</span><span class="sxs-lookup"><span data-stu-id="b853e-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-123">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="b853e-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-124">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="b853e-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="b853e-125">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XNode> (incluyendo <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="b853e-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="b853e-126">Método</span><span class="sxs-lookup"><span data-stu-id="b853e-126">Method</span></span>|<span data-ttu-id="b853e-127">Description</span><span class="sxs-lookup"><span data-stu-id="b853e-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-128">Reemplaza un nodo por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="b853e-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="b853e-129">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="b853e-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="b853e-130">Método</span><span class="sxs-lookup"><span data-stu-id="b853e-130">Method</span></span>|<span data-ttu-id="b853e-131">Description</span><span class="sxs-lookup"><span data-stu-id="b853e-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="b853e-132">Reemplaza los nodos secundarios por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="b853e-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b853e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b853e-133">See Also</span></span>  
 [<span data-ttu-id="b853e-134">Modificar árboles XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b853e-134">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
