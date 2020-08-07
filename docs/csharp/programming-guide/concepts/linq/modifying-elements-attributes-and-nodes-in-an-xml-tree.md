---
title: Modificar elementos, atributos y nodos de un árbol XML
description: Aprenda sobre los métodos y las propiedades que puede utilizar para modificar un elemento, sus nodos secundarios o sus atributos.
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: bfff882dc57a4f6f4b228563ac923122097d88d0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303171"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="a37c2-103">Modificar elementos, atributos y nodos de un árbol XML</span><span class="sxs-lookup"><span data-stu-id="a37c2-103">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="a37c2-104">La tabla siguiente resume los métodos y las propiedades que puede usar para modificar un elemento, sus elementos secundarios o sus atributos.</span><span class="sxs-lookup"><span data-stu-id="a37c2-104">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="a37c2-105">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a37c2-105">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="a37c2-106">Método</span><span class="sxs-lookup"><span data-stu-id="a37c2-106">Method</span></span>|<span data-ttu-id="a37c2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a37c2-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-108">Reemplaza un elemento por XML analizado.</span><span class="sxs-lookup"><span data-stu-id="a37c2-108">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-109">Quita todo el contenido (atributos y nodos secundarios) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="a37c2-109">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-110">Quita los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="a37c2-110">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-111">Reemplaza todo el contenido (nodos secundarios y atributos) de un elemento.</span><span class="sxs-lookup"><span data-stu-id="a37c2-111">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-112">Reemplaza los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="a37c2-112">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-113">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="a37c2-113">Sets the value of an attribute.</span></span> <span data-ttu-id="a37c2-114">Crea el atributo si no existe.</span><span class="sxs-lookup"><span data-stu-id="a37c2-114">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="a37c2-115">Si el valor se establece en `null`, quita el atributo.</span><span class="sxs-lookup"><span data-stu-id="a37c2-115">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-116">Establece el valor de un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="a37c2-116">Sets the value of a child element.</span></span> <span data-ttu-id="a37c2-117">Crea el elemento si no existe.</span><span class="sxs-lookup"><span data-stu-id="a37c2-117">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="a37c2-118">Si el valor se establece en `null`, quita el elemento.</span><span class="sxs-lookup"><span data-stu-id="a37c2-118">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-119">Reemplaza el contenido (nodos secundarios) de un elemento por el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="a37c2-119">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-120">Establece el valor de un elemento.</span><span class="sxs-lookup"><span data-stu-id="a37c2-120">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="a37c2-121">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a37c2-121">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="a37c2-122">Método</span><span class="sxs-lookup"><span data-stu-id="a37c2-122">Method</span></span>|<span data-ttu-id="a37c2-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a37c2-123">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-124">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="a37c2-124">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-125">Establece el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="a37c2-125">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="a37c2-126">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XNode> (incluyendo <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="a37c2-126">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="a37c2-127">Método</span><span class="sxs-lookup"><span data-stu-id="a37c2-127">Method</span></span>|<span data-ttu-id="a37c2-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="a37c2-128">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-129">Reemplaza un nodo por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="a37c2-129">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="a37c2-130">Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="a37c2-130">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="a37c2-131">Método</span><span class="sxs-lookup"><span data-stu-id="a37c2-131">Method</span></span>|<span data-ttu-id="a37c2-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="a37c2-132">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="a37c2-133">Reemplaza los nodos secundarios por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="a37c2-133">Replaces the children nodes with new content.</span></span>|  
