---
title: Obtener acceso a XML en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756967"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="ab44a-102">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab44a-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="ab44a-103">Visual Basic proporciona propiedades de eje XML para obtener acceso y navegar por [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] estructuras.</span><span class="sxs-lookup"><span data-stu-id="ab44a-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="ab44a-104">Estas propiedades usan una sintaxis especial para que pueda tener acceso a los elementos y atributos especificando los nombres XML.</span><span class="sxs-lookup"><span data-stu-id="ab44a-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="ab44a-105">En la tabla siguiente se enumera las características del lenguaje que permiten tener acceso a los elementos XML y atributos en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab44a-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="ab44a-106">Propiedades de eje XML</span><span class="sxs-lookup"><span data-stu-id="ab44a-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="ab44a-107">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="ab44a-107">Property description</span></span>|<span data-ttu-id="ab44a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab44a-108">Example</span></span>|<span data-ttu-id="ab44a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab44a-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="ab44a-110">*eje child*</span><span class="sxs-lookup"><span data-stu-id="ab44a-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="ab44a-111">Obtiene todos los `phone` elementos que son elementos secundarios de la `contact` elemento.</span><span class="sxs-lookup"><span data-stu-id="ab44a-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="ab44a-112">*eje de atributo*</span><span class="sxs-lookup"><span data-stu-id="ab44a-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="ab44a-113">Obtiene todos los `type` los atributos de la `phone` elemento.</span><span class="sxs-lookup"><span data-stu-id="ab44a-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="ab44a-114">*eje descendiente*</span><span class="sxs-lookup"><span data-stu-id="ab44a-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="ab44a-115">Obtiene todos los `name` elementos de la `contacts` elemento, independientemente de la profundidad de la jerarquía que se producen.</span><span class="sxs-lookup"><span data-stu-id="ab44a-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="ab44a-116">*indizador de extensión*</span><span class="sxs-lookup"><span data-stu-id="ab44a-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="ab44a-117">Obtiene el primer `name` elemento de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ab44a-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="ab44a-118">*value*</span><span class="sxs-lookup"><span data-stu-id="ab44a-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="ab44a-119">Obtiene la representación de cadena del primer objeto de la secuencia, o `Nothing` si la secuencia está vacía.</span><span class="sxs-lookup"><span data-stu-id="ab44a-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="ab44a-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ab44a-120">In This Section</span></span>  
 [<span data-ttu-id="ab44a-121">Cómo: Acceso a los elementos descendientes XML</span><span class="sxs-lookup"><span data-stu-id="ab44a-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="ab44a-122">Se muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tiene un nombre especificado y que se incluyen en un elemento XML especificado.</span><span class="sxs-lookup"><span data-stu-id="ab44a-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="ab44a-123">Cómo: Elementos secundarios XML de acceso</span><span class="sxs-lookup"><span data-stu-id="ab44a-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="ab44a-124">Muestra cómo utilizar a un elemento secundario de la propiedad de eje para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ab44a-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="ab44a-125">Cómo: Atributos XML de acceso</span><span class="sxs-lookup"><span data-stu-id="ab44a-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="ab44a-126">Se muestra cómo usar una propiedad de eje de atributo para tener acceso a todos los atributos XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ab44a-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="ab44a-127">Cómo: Declarar y usar prefijos de Namespace XML</span><span class="sxs-lookup"><span data-stu-id="ab44a-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="ab44a-128">Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y tener acceso a elementos XML.</span><span class="sxs-lookup"><span data-stu-id="ab44a-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ab44a-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ab44a-129">Related Sections</span></span>  
 [<span data-ttu-id="ab44a-130">Propiedades del eje XML</span><span class="sxs-lookup"><span data-stu-id="ab44a-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="ab44a-131">Proporciona vínculos a secciones que describen las diversas propiedades de acceso XML.</span><span class="sxs-lookup"><span data-stu-id="ab44a-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="ab44a-132">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab44a-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="ab44a-133">Proporciona una introducción al uso [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab44a-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ab44a-134">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab44a-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="ab44a-135">Proporciona una introducción al uso de literales XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab44a-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ab44a-136">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ab44a-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="ab44a-137">Proporciona vínculos a secciones sobre cómo cargar y modificar XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab44a-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="ab44a-138">XML</span><span class="sxs-lookup"><span data-stu-id="ab44a-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="ab44a-139">Proporciona vínculos a secciones que describen cómo utilizar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab44a-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
