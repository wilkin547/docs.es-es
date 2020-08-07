---
title: Información general de la clase XElement (C#)
description: La clase XElement representa un elemento XML en C#. Esta clase es una de las clases fundamentales de LINQ to XML. Aprenda sobre la funcionalidad que proporciona XElement.
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: f76f51703de054443f47531294777b43a9c0b004
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302183"
---
# <a name="xelement-class-overview-c"></a><span data-ttu-id="44fbc-105">Información general de la clase XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="44fbc-105">XElement Class Overview (C#)</span></span>
<span data-ttu-id="44fbc-106">La clase <xref:System.Xml.Linq.XElement> es una de las clases fundamentales de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44fbc-106">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="44fbc-107">Representa a un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="44fbc-107">It represents an XML element.</span></span> <span data-ttu-id="44fbc-108">Puede utilizar esta clase para crear elementos; cambiar el contenido del elemento; agregar, modificar o eliminar elementos secundarios; agregar atributos a un elemento; o serializar el contenido de un elemento en forma de texto.</span><span class="sxs-lookup"><span data-stu-id="44fbc-108">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="44fbc-109">También puede operar con otras clases de <xref:System.Xml?displayProperty=nameWithType>, como son <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="44fbc-109">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
<span data-ttu-id="44fbc-110">Este tema describe la funcionalidad que ofrece la clase <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="44fbc-110">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
## <a name="constructing-xml-trees"></a><span data-ttu-id="44fbc-111">Construir árboles XML</span><span class="sxs-lookup"><span data-stu-id="44fbc-111">Constructing XML Trees</span></span>  
 <span data-ttu-id="44fbc-112">Es posible construir árboles XML de diferentes formas, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="44fbc-112">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="44fbc-113">Puede construir un árbol XML mediante código.</span><span class="sxs-lookup"><span data-stu-id="44fbc-113">You can construct an XML tree in code.</span></span> <span data-ttu-id="44fbc-114">Para obtener más información, consulte [Crear árboles XML (C#)](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="44fbc-114">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
- <span data-ttu-id="44fbc-115">Puede analizar XML a partir de diferentes orígenes, incluyendo un <xref:System.IO.TextReader>, archivos de texto o direcciones web (URL).</span><span class="sxs-lookup"><span data-stu-id="44fbc-115">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="44fbc-116">Para obtener más información, consulte [Analizar XML (C#)](./how-to-parse-a-string.md).</span><span class="sxs-lookup"><span data-stu-id="44fbc-116">For more information, see [Parsing XML (C#)](./how-to-parse-a-string.md).</span></span>  
  
- <span data-ttu-id="44fbc-117">También puede utilizar un <xref:System.Xml.XmlReader> para rellenar el árbol.</span><span class="sxs-lookup"><span data-stu-id="44fbc-117">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="44fbc-118">Para obtener más información, vea <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="44fbc-118">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="44fbc-119">Si dispone de un módulo que pueda escribir contenidos en un <xref:System.Xml.XmlWriter>, puede utilizar el método <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear un sistema de escritura, para pasar éste al módulo y para utilizar después el contenido que se haya escrito en <xref:System.Xml.XmlWriter> para rellenar el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="44fbc-119">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="44fbc-120">No obstante, la forma más habitual de crear un árbol XML es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="44fbc-120">However, the most common way to create an XML tree is as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="44fbc-121">Otra técnica que se usa con frecuencia para crear un árbol XML implica el uso de los resultados de una consulta LINK para rellenar el árbol XML, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="44fbc-121">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="44fbc-122">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="44fbc-122">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a><span data-ttu-id="44fbc-123">Serializar árboles XML</span><span class="sxs-lookup"><span data-stu-id="44fbc-123">Serializing XML Trees</span></span>  
 <span data-ttu-id="44fbc-124">Puede serializar un árbol XML en un <xref:System.IO.File>, un <xref:System.IO.TextWriter> o en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="44fbc-124">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="44fbc-125">Para obtener más información, consulte [Serializar árboles XML (C#)](./preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="44fbc-125">For more information, see [Serializing XML Trees (C#)](./preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="44fbc-126">Recuperar datos XML mediante los métodos de los ejes</span><span class="sxs-lookup"><span data-stu-id="44fbc-126">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="44fbc-127">Puede utilizar los métodos de los ejes para recuperar atributos, elementos secundarios, elementos descendientes y elementos antecesores.</span><span class="sxs-lookup"><span data-stu-id="44fbc-127">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="44fbc-128">Las consultas LINK operan sobre métodos de eje y proporcionan varias formas flexibles y eficaces de recorrer y procesar árboles XML.</span><span class="sxs-lookup"><span data-stu-id="44fbc-128">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="44fbc-129">Para obtener más información, consulte [Ejes de LINQ to XML (C#)](./linq-to-xml-axes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="44fbc-129">For more information, see [LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md).</span></span>  
  
## <a name="querying-xml-trees"></a><span data-ttu-id="44fbc-130">Consultar árboles XML</span><span class="sxs-lookup"><span data-stu-id="44fbc-130">Querying XML Trees</span></span>  
 <span data-ttu-id="44fbc-131">Puede escribir consultas LINK que extraigan datos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="44fbc-131">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="44fbc-132">Para obtener más información, consulte [Consultar árboles XML (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="44fbc-132">For more information, see [Querying XML Trees (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span></span>  
  
## <a name="modifying-xml-trees"></a><span data-ttu-id="44fbc-133">Modificar árboles XML</span><span class="sxs-lookup"><span data-stu-id="44fbc-133">Modifying XML Trees</span></span>  
 <span data-ttu-id="44fbc-134">Puede modificar un elemento de diferentes maneras, incluyendo el cambiar su contenido o sus atributos.</span><span class="sxs-lookup"><span data-stu-id="44fbc-134">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="44fbc-135">También puede eliminar un elemento dependiente de un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="44fbc-135">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="44fbc-136">Para obtener más información, consulte [Modificar árboles XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="44fbc-136">For more information, see [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44fbc-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44fbc-137">See also</span></span>

- [<span data-ttu-id="44fbc-138">Información general sobre la programación de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="44fbc-138">LINQ to XML Programming Overview (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
