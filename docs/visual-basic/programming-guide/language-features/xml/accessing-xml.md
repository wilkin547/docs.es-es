---
title: Obtener acceso a XML en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 79c7b8a94731e151a803a041d91dd1e240ddeb97
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="edd60-102">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edd60-102">Accessing XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="edd60-103">Proporciona propiedades de eje XML para obtener acceso y navegar por [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] estructuras.</span><span class="sxs-lookup"><span data-stu-id="edd60-103"> provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="edd60-104">Estas propiedades utilizan una sintaxis especial que le permite tener acceso a elementos y atributos especificando los nombres XML.</span><span class="sxs-lookup"><span data-stu-id="edd60-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="edd60-105">En la tabla siguiente se enumera las características de lenguaje que permiten obtener acceso a elementos y atributos en XML [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edd60-105">The following table lists the language features that enable you to access XML elements and attributes in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="edd60-106">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="edd60-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="edd60-107">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="edd60-107">Property description</span></span>|<span data-ttu-id="edd60-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edd60-108">Example</span></span>|<span data-ttu-id="edd60-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="edd60-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="edd60-110">*eje child*</span><span class="sxs-lookup"><span data-stu-id="edd60-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="edd60-111">Obtiene todos los `phone` elementos que son elementos secundarios de la `contact` elemento.</span><span class="sxs-lookup"><span data-stu-id="edd60-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="edd60-112">*eje de atributo*</span><span class="sxs-lookup"><span data-stu-id="edd60-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="edd60-113">Obtiene todos los `type` atributos de la `phone` elemento.</span><span class="sxs-lookup"><span data-stu-id="edd60-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="edd60-114">*eje Descendant*</span><span class="sxs-lookup"><span data-stu-id="edd60-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="edd60-115">Obtiene todos los `name` elementos de la `contacts` elemento, independientemente de la profundidad de la jerarquía que se produzcan.</span><span class="sxs-lookup"><span data-stu-id="edd60-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="edd60-116">*indizador de extensión*</span><span class="sxs-lookup"><span data-stu-id="edd60-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="edd60-117">Obtiene la primera `name` elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="edd60-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="edd60-118">*value*</span><span class="sxs-lookup"><span data-stu-id="edd60-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="edd60-119">Obtiene la representación de cadena del primer objeto de la secuencia, o `Nothing` si la secuencia está vacía.</span><span class="sxs-lookup"><span data-stu-id="edd60-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="edd60-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="edd60-120">In This Section</span></span>  
 [<span data-ttu-id="edd60-121">Acceso a elementos descendientes XML</span><span class="sxs-lookup"><span data-stu-id="edd60-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="edd60-122">Muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen el nombre especificado y que están incluidos en un elemento XML especificado.</span><span class="sxs-lookup"><span data-stu-id="edd60-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="edd60-123">Acceso a elementos secundarios XML</span><span class="sxs-lookup"><span data-stu-id="edd60-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="edd60-124">Muestra cómo utilizar a un elemento secundario de la propiedad de eje para tener acceso a todos los elementos secundarios XML que tienen el nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="edd60-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="edd60-125">Acceso a atributos XML</span><span class="sxs-lookup"><span data-stu-id="edd60-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="edd60-126">Muestra cómo utilizar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen el nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="edd60-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="edd60-127">Declarar y usar prefijos de espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="edd60-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="edd60-128">Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y tener acceso a elementos XML.</span><span class="sxs-lookup"><span data-stu-id="edd60-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="edd60-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="edd60-129">Related Sections</span></span>  
 [<span data-ttu-id="edd60-130">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="edd60-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="edd60-131">Proporciona vínculos a secciones que describen las diversas propiedades de acceso XML.</span><span class="sxs-lookup"><span data-stu-id="edd60-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="edd60-132">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edd60-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="edd60-133">Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="edd60-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="edd60-134">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edd60-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="edd60-135">Proporciona una introducción al uso de literales XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="edd60-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="edd60-136">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edd60-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="edd60-137">Proporciona vínculos a secciones sobre cómo cargar y modificar XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="edd60-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="edd60-138">XML</span><span class="sxs-lookup"><span data-stu-id="edd60-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="edd60-139">Proporciona vínculos a secciones que describen cómo utilizar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="edd60-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
