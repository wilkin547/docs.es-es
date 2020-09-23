---
title: Acceso a XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 8ffe6d5ed368aee6d6984ec6ab28c8832921a3f8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080184"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="615e9-102">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="615e9-102">Accessing XML in Visual Basic</span></span>

<span data-ttu-id="615e9-103">Visual Basic proporciona propiedades de eje XML para tener acceso a las estructuras y navegar por ellas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="615e9-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="615e9-104">Estas propiedades usan una sintaxis especial para permitir el acceso a elementos y atributos mediante la especificación de los nombres XML.</span><span class="sxs-lookup"><span data-stu-id="615e9-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="615e9-105">En la tabla siguiente se enumeran las características del lenguaje que permiten tener acceso a los elementos y atributos XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="615e9-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="615e9-106">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="615e9-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="615e9-107">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="615e9-107">Property description</span></span>|<span data-ttu-id="615e9-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="615e9-108">Example</span></span>|<span data-ttu-id="615e9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="615e9-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="615e9-110">*eje child*</span><span class="sxs-lookup"><span data-stu-id="615e9-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="615e9-111">Obtiene todos los `phone` elementos que son elementos secundarios del `contact` elemento.</span><span class="sxs-lookup"><span data-stu-id="615e9-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="615e9-112">*eje de atributo*</span><span class="sxs-lookup"><span data-stu-id="615e9-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="615e9-113">Obtiene todos los `type` atributos del `phone` elemento.</span><span class="sxs-lookup"><span data-stu-id="615e9-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="615e9-114">*eje descendant*</span><span class="sxs-lookup"><span data-stu-id="615e9-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="615e9-115">Obtiene todos los `name` elementos del `contacts` elemento, independientemente de la profundidad de la jerarquía en la que se producen.</span><span class="sxs-lookup"><span data-stu-id="615e9-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="615e9-116">*indexador de extensión*</span><span class="sxs-lookup"><span data-stu-id="615e9-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="615e9-117">Obtiene el primer `name` elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="615e9-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="615e9-118">*value*</span><span class="sxs-lookup"><span data-stu-id="615e9-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="615e9-119">Obtiene la representación en forma de cadena del primer objeto de la secuencia o `Nothing` si la secuencia está vacía.</span><span class="sxs-lookup"><span data-stu-id="615e9-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="615e9-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="615e9-120">In This Section</span></span>  

 [<span data-ttu-id="615e9-121">Procedimiento para obtener acceso a elementos descendientes XML</span><span class="sxs-lookup"><span data-stu-id="615e9-121">How to: Access XML Descendant Elements</span></span>](how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="615e9-122">Muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML especificado.</span><span class="sxs-lookup"><span data-stu-id="615e9-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="615e9-123">Procedimiento para obtener acceso a elementos secundarios XML</span><span class="sxs-lookup"><span data-stu-id="615e9-123">How to: Access XML Child Elements</span></span>](how-to-access-xml-child-elements.md)  
 <span data-ttu-id="615e9-124">Muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="615e9-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="615e9-125">Procedimiento para obtener acceso a atributos XML</span><span class="sxs-lookup"><span data-stu-id="615e9-125">How to: Access XML Attributes</span></span>](how-to-access-xml-attributes.md)  
 <span data-ttu-id="615e9-126">Muestra cómo utilizar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="615e9-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="615e9-127">Procedimiento para declarar y usar prefijos de espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="615e9-127">How to: Declare and Use XML Namespace Prefixes</span></span>](how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="615e9-128">Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y obtener acceso a los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="615e9-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="615e9-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="615e9-129">Related Sections</span></span>  

 [<span data-ttu-id="615e9-130">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="615e9-130">XML Axis Properties</span></span>](../../../language-reference/xml-axis/index.md)  
 <span data-ttu-id="615e9-131">Proporciona vínculos a secciones en las que se describen las distintas propiedades de acceso XML.</span><span class="sxs-lookup"><span data-stu-id="615e9-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="615e9-132">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="615e9-132">Overview of LINQ to XML in Visual Basic</span></span>](overview-of-linq-to-xml.md)  
 <span data-ttu-id="615e9-133">Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] de en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="615e9-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="615e9-134">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="615e9-134">Creating XML in Visual Basic</span></span>](creating-xml.md)  
 <span data-ttu-id="615e9-135">Proporciona una introducción al uso de literales XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="615e9-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="615e9-136">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="615e9-136">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)  
 <span data-ttu-id="615e9-137">Proporciona vínculos a las secciones sobre cómo cargar y modificar XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="615e9-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="615e9-138">XML</span><span class="sxs-lookup"><span data-stu-id="615e9-138">XML</span></span>](index.md)  
 <span data-ttu-id="615e9-139">Proporciona vínculos a secciones que describen cómo usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="615e9-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
