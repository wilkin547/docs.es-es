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
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351747"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="ac2e2-102">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac2e2-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="ac2e2-103">Visual Basic proporciona propiedades de eje XML para tener acceso a las estructuras de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] y navegar por ellas.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="ac2e2-104">Estas propiedades usan una sintaxis especial para permitir el acceso a elementos y atributos mediante la especificación de los nombres XML.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="ac2e2-105">En la tabla siguiente se enumeran las características del lenguaje que permiten tener acceso a los elementos y atributos XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="ac2e2-106">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="ac2e2-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="ac2e2-107">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="ac2e2-107">Property description</span></span>|<span data-ttu-id="ac2e2-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac2e2-108">Example</span></span>|<span data-ttu-id="ac2e2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac2e2-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="ac2e2-110">*eje secundario*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="ac2e2-111">Obtiene todos los elementos de `phone` que son elementos secundarios del elemento `contact`.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="ac2e2-112">*eje de atributo*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="ac2e2-113">Obtiene todos los atributos `type` del elemento `phone`.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="ac2e2-114">*eje descendiente*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="ac2e2-115">Obtiene todos los elementos `name` del elemento `contacts`, independientemente de la profundidad de la jerarquía que se produzcan.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="ac2e2-116">*indexador de extensión*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="ac2e2-117">Obtiene el primer elemento `name` de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="ac2e2-118">*valor*</span><span class="sxs-lookup"><span data-stu-id="ac2e2-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="ac2e2-119">Obtiene la representación de cadena del primer objeto de la secuencia o `Nothing` si la secuencia está vacía.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="ac2e2-120">Esta sección</span><span class="sxs-lookup"><span data-stu-id="ac2e2-120">In This Section</span></span>  
 [<span data-ttu-id="ac2e2-121">Acceso a elementos descendientes XML</span><span class="sxs-lookup"><span data-stu-id="ac2e2-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="ac2e2-122">Muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML especificado.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="ac2e2-123">Acceso a elementos secundarios XML</span><span class="sxs-lookup"><span data-stu-id="ac2e2-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="ac2e2-124">Muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="ac2e2-125">Acceso a atributos XML</span><span class="sxs-lookup"><span data-stu-id="ac2e2-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="ac2e2-126">Muestra cómo utilizar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="ac2e2-127">Declarar y usar prefijos de espacio de nombres XML</span><span class="sxs-lookup"><span data-stu-id="ac2e2-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="ac2e2-128">Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y obtener acceso a los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ac2e2-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ac2e2-129">Related Sections</span></span>  
 [<span data-ttu-id="ac2e2-130">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="ac2e2-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="ac2e2-131">Proporciona vínculos a secciones en las que se describen las distintas propiedades de acceso XML.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="ac2e2-132">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac2e2-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="ac2e2-133">Proporciona una introducción al uso de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ac2e2-134">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac2e2-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="ac2e2-135">Proporciona una introducción al uso de literales XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ac2e2-136">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac2e2-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="ac2e2-137">Proporciona vínculos a las secciones sobre cómo cargar y modificar XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ac2e2-138">XML</span><span class="sxs-lookup"><span data-stu-id="ac2e2-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="ac2e2-139">Proporciona vínculos a secciones en las que se describe cómo usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ac2e2-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
