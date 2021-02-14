---
description: Más información acerca de cómo obtener acceso a XML en Visual Basic
title: Acceso a XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 2d77b2aa5f4136095ce5684976fe3ba03be7c28c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462664"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="8dfa2-103">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dfa2-103">Accessing XML in Visual Basic</span></span>

<span data-ttu-id="8dfa2-104">Visual Basic proporciona propiedades de eje XML para tener acceso a las estructuras y navegar por ellas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8dfa2-104">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="8dfa2-105">Estas propiedades usan una sintaxis especial para permitir el acceso a elementos y atributos mediante la especificación de los nombres XML.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-105">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="8dfa2-106">En la tabla siguiente se enumeran las características del lenguaje que permiten tener acceso a los elementos y atributos XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-106">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="8dfa2-107">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="8dfa2-107">XML Axis Properties</span></span>  
  
|<span data-ttu-id="8dfa2-108">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="8dfa2-108">Property description</span></span>|<span data-ttu-id="8dfa2-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dfa2-109">Example</span></span>|<span data-ttu-id="8dfa2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dfa2-110">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="8dfa2-111">*eje child*</span><span class="sxs-lookup"><span data-stu-id="8dfa2-111">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="8dfa2-112">Obtiene todos los `phone` elementos que son elementos secundarios del `contact` elemento.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-112">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="8dfa2-113">*eje de atributo*</span><span class="sxs-lookup"><span data-stu-id="8dfa2-113">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="8dfa2-114">Obtiene todos los `type` atributos del `phone` elemento.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-114">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="8dfa2-115">*eje descendant*</span><span class="sxs-lookup"><span data-stu-id="8dfa2-115">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="8dfa2-116">Obtiene todos los `name` elementos del `contacts` elemento, independientemente de la profundidad de la jerarquía en la que se producen.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-116">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="8dfa2-117">*indexador de extensión*</span><span class="sxs-lookup"><span data-stu-id="8dfa2-117">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="8dfa2-118">Obtiene el primer `name` elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-118">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="8dfa2-119">*value*</span><span class="sxs-lookup"><span data-stu-id="8dfa2-119">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="8dfa2-120">Obtiene la representación en forma de cadena del primer objeto de la secuencia o `Nothing` si la secuencia está vacía.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-120">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="8dfa2-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8dfa2-121">In This Section</span></span>  

 [<span data-ttu-id="8dfa2-122">Procedimiento para obtener acceso a elementos descendientes XML</span><span class="sxs-lookup"><span data-stu-id="8dfa2-122">How to: Access XML Descendant Elements</span></span>](how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="8dfa2-123">Muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML especificado.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-123">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="8dfa2-124">Procedimiento para obtener acceso a elementos secundarios XML</span><span class="sxs-lookup"><span data-stu-id="8dfa2-124">How to: Access XML Child Elements</span></span>](how-to-access-xml-child-elements.md)  
 <span data-ttu-id="8dfa2-125">Muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-125">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="8dfa2-126">Procedimiento para obtener acceso a atributos XML</span><span class="sxs-lookup"><span data-stu-id="8dfa2-126">How to: Access XML Attributes</span></span>](how-to-access-xml-attributes.md)  
 <span data-ttu-id="8dfa2-127">Muestra cómo utilizar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-127">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="8dfa2-128">Procedimiento para declarar y usar prefijos de espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="8dfa2-128">How to: Declare and Use XML Namespace Prefixes</span></span>](how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="8dfa2-129">Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y obtener acceso a los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-129">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8dfa2-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8dfa2-130">Related Sections</span></span>  

 [<span data-ttu-id="8dfa2-131">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="8dfa2-131">XML Axis Properties</span></span>](../../../language-reference/xml-axis/index.md)  
 <span data-ttu-id="8dfa2-132">Proporciona vínculos a secciones en las que se describen las distintas propiedades de acceso XML.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-132">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="8dfa2-133">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dfa2-133">Overview of LINQ to XML in Visual Basic</span></span>](overview-of-linq-to-xml.md)  
 <span data-ttu-id="8dfa2-134">Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] de en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-134">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8dfa2-135">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dfa2-135">Creating XML in Visual Basic</span></span>](creating-xml.md)  
 <span data-ttu-id="8dfa2-136">Proporciona una introducción al uso de literales XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-136">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8dfa2-137">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dfa2-137">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)  
 <span data-ttu-id="8dfa2-138">Proporciona vínculos a las secciones sobre cómo cargar y modificar XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-138">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8dfa2-139">XML</span><span class="sxs-lookup"><span data-stu-id="8dfa2-139">XML</span></span>](index.md)  
 <span data-ttu-id="8dfa2-140">Proporciona vínculos a secciones que describen cómo usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dfa2-140">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
