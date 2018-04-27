---
title: Ejes integrados en el lenguaje de Visual Basic (LINQ to XML)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8360281d1d8de0cad243297cd78e97958530bae4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="e0c1e-102">Ejes integrados en el lenguaje de Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="e0c1e-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="e0c1e-103">Esta sección describen características integradas directamente en el lenguaje de Visual Basic que resulte sencillo tener acceso a XML.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-103">This section describes features built directly into the Visual Basic language to make it easy to access XML.</span></span> <span data-ttu-id="e0c1e-104">Muchos de los ejemplos de LINQ para documentación XML usan estos ejes integrados de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-104">Many of the examples in the LINQ to XML documentation use these integrated Visual Basic axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0c1e-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e0c1e-105">In This Section</span></span>  
  
|<span data-ttu-id="e0c1e-106">Tema</span><span class="sxs-lookup"><span data-stu-id="e0c1e-106">Topic</span></span>|<span data-ttu-id="e0c1e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0c1e-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e0c1e-108">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="e0c1e-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="e0c1e-109">Proporciona el acceso a los elementos secundarios de uno de los siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="e0c1e-110">Este eje es equivalente al eje <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="e0c1e-111">Propiedad del eje descendiente XML</span><span class="sxs-lookup"><span data-stu-id="e0c1e-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="e0c1e-112">Proporciona acceso a los descendientes de: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument> o una recopilación de objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e0c1e-113">Este eje es equivalente al eje <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="e0c1e-114">Propiedad del eje de atributo XML</span><span class="sxs-lookup"><span data-stu-id="e0c1e-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="e0c1e-115">Proporciona acceso a un atributo de un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="e0c1e-116">Este eje es en líneas generales equivalente al eje <xref:System.Xml.Linq.XElement.Attribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="e0c1e-117">Este eje difiere del eje <xref:System.Xml.Linq.XElement.Attribute%2A> en que devuelve el valor del atributo, no un objeto <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="e0c1e-118">Propiedad de indexador de extensión</span><span class="sxs-lookup"><span data-stu-id="e0c1e-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="e0c1e-119">Proporciona acceso a los elementos individuales de una recopilación.</span><span class="sxs-lookup"><span data-stu-id="e0c1e-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0c1e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0c1e-120">See Also</span></span>  
 [<span data-ttu-id="e0c1e-121">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0c1e-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
