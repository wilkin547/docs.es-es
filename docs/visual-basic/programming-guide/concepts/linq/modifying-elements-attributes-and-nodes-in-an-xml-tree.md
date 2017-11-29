---
title: Modificar elementos, atributos y nodos en un Tree1 XML
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1c769885d958abeaa92e19ef0b20d695fbcc4b96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="9690b-102">Modificar elementos, atributos y nodos de un árbol XML</span><span class="sxs-lookup"><span data-stu-id="9690b-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="9690b-103">La tabla siguiente resume los métodos y las propiedades que puede usar para modificar un elemento, sus elementos secundarios o sus atributos.</span><span class="sxs-lookup"><span data-stu-id="9690b-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="9690b-104">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="9690b-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="9690b-105">Método</span><span class="sxs-lookup"><span data-stu-id="9690b-105">Method</span></span>|<span data-ttu-id="9690b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9690b-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-107">Reemplaza un elemento por XML analizado.</span><span class="sxs-lookup"><span data-stu-id="9690b-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-108">Quita todo el contenido (atributos y nodos secundarios) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9690b-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-109">Quita los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9690b-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-110">Reemplaza todo el contenido (nodos secundarios y atributos) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9690b-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-111">Reemplaza los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9690b-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-112">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="9690b-112">Sets the value of an attribute.</span></span> <span data-ttu-id="9690b-113">Crea el atributo si no existe.</span><span class="sxs-lookup"><span data-stu-id="9690b-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="9690b-114">Si el valor se establece en `null`, quita el atributo.</span><span class="sxs-lookup"><span data-stu-id="9690b-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-115">Establece el valor de un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="9690b-115">Sets the value of a child element.</span></span> <span data-ttu-id="9690b-116">Crea el elemento si no existe.</span><span class="sxs-lookup"><span data-stu-id="9690b-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="9690b-117">Si el valor se establece en `null`, quita el elemento.</span><span class="sxs-lookup"><span data-stu-id="9690b-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-118">Reemplaza el contenido (nodos secundarios) de un elemento por el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="9690b-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-119">Establece el valor de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9690b-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="9690b-120">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9690b-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="9690b-121">Método</span><span class="sxs-lookup"><span data-stu-id="9690b-121">Method</span></span>|<span data-ttu-id="9690b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9690b-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-123">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="9690b-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-124">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="9690b-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="9690b-125">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XNode> (incluyendo <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="9690b-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="9690b-126">Método</span><span class="sxs-lookup"><span data-stu-id="9690b-126">Method</span></span>|<span data-ttu-id="9690b-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9690b-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-128">Reemplaza un nodo por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="9690b-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="9690b-129">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="9690b-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="9690b-130">Método</span><span class="sxs-lookup"><span data-stu-id="9690b-130">Method</span></span>|<span data-ttu-id="9690b-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="9690b-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="9690b-132">Reemplaza los nodos secundarios por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="9690b-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9690b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9690b-133">See Also</span></span>  
 [<span data-ttu-id="9690b-134">Modificar árboles XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9690b-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
