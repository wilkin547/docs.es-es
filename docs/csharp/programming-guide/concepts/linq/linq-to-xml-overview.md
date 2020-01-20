---
title: Información general de LINQ to XML (C#)
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: d8b606e1d3287f13a2112b75d5239fd1ac7dd7dc
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635514"
---
# <a name="linq-to-xml-overview-c"></a><span data-ttu-id="90f1d-102">Información general de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="90f1d-102">LINQ to XML Overview (C#)</span></span>

<span data-ttu-id="90f1d-103">LINQ to XML proporciona una interfaz de programación XML en memoria que aprovecha .NET Language-Integrated Query (LINQ) Framework.</span><span class="sxs-lookup"><span data-stu-id="90f1d-103">LINQ to XML provides an in-memory XML programming interface that leverages the .NET Language-Integrated Query (LINQ) Framework.</span></span> <span data-ttu-id="90f1d-104">LINQ to XML utiliza las características de .NET y es comparable a una actualizada y rediseñada interfaz de programación XML para el Modelo de objetos de documento (DOM).</span><span class="sxs-lookup"><span data-stu-id="90f1d-104">LINQ to XML uses .NET capabilities and is comparable to an updated, redesigned Document Object Model (DOM) XML programming interface.</span></span> 
 
<span data-ttu-id="90f1d-105">XML se ha adoptado ampliamente como un modo de dar formato a datos en diversos contextos.</span><span class="sxs-lookup"><span data-stu-id="90f1d-105">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="90f1d-106">Por ejemplo, puede encontrar XML en la web, en archivos de configuración, en archivos de Microsoft Office Word y en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="90f1d-106">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="90f1d-107">es un método actualizado y rediseñado para la programación con XML.</span><span class="sxs-lookup"><span data-stu-id="90f1d-107">is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="90f1d-108">Proporciona las funcionalidades de modificación de documentos en memoria del Modelo de objetos de documento (DOM) y es compatible con expresiones de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="90f1d-108">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports LINQ query expressions.</span></span> <span data-ttu-id="90f1d-109">Aunque estas expresiones de consulta difieren sintácticamente de XPath, proporcionan una funcionalidad similar.</span><span class="sxs-lookup"><span data-stu-id="90f1d-109">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>

## <a name="linq-to-xml-developers"></a><span data-ttu-id="90f1d-110">Desarrolladores de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="90f1d-110">LINQ to XML Developers</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="90f1d-111">se dirige a diversos desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="90f1d-111">targets a variety of developers.</span></span> <span data-ttu-id="90f1d-112">Para el desarrollador medio que solo desea completar una tarea, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica el código XML al proporcionar una experiencia de consulta similar a SQL.</span><span class="sxs-lookup"><span data-stu-id="90f1d-112">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="90f1d-113">Con un poco de estudio, los programadores pueden aprender a escribir consultas sucintas y eficaces en el lenguaje de programación que prefieran.</span><span class="sxs-lookup"><span data-stu-id="90f1d-113">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>

<span data-ttu-id="90f1d-114">Los desarrolladores profesionales pueden usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para aumentar considerablemente su productividad.</span><span class="sxs-lookup"><span data-stu-id="90f1d-114">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="90f1d-115">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], pueden escribir menos código, que a su vez resulte más expresivo, compacto y eficaz.</span><span class="sxs-lookup"><span data-stu-id="90f1d-115">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="90f1d-116">Pueden usar expresiones de consulta de distintos dominios de datos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="90f1d-116">They can use query expressions from multiple data domains at the same time.</span></span>

## <a name="what-is-linq-to-xml"></a><span data-ttu-id="90f1d-117">¿Qué es LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="90f1d-117">What Is LINQ to XML?</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="90f1d-118">es una interfaz de programación XML en memoria y habilitada para LINQ que permite trabajar con XML desde los lenguajes de programación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90f1d-118">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET Framework programming languages.</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="90f1d-119">se parece a Document Object Model (DOM) en lo que respecta a la inserción del documento XML en la memoria.</span><span class="sxs-lookup"><span data-stu-id="90f1d-119">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="90f1d-120">Puede consultar y modificar el documento; una vez modificado, puede guardarlo en un archivo o serializarlo y enviarlo a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="90f1d-120">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="90f1d-121">Pero [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es diferente de DOM: proporciona un nuevo modelo de objetos más ligero, con el que se trabaja más fácilmente y que aprovecha las características de lenguaje de C#.</span><span class="sxs-lookup"><span data-stu-id="90f1d-121">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in C#.</span></span>

<span data-ttu-id="90f1d-122">La ventaja más importante de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es su integración con Language-Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="90f1d-122">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="90f1d-123">Esta integración permite escribir consultas en el documento XML en memoria para recuperar colecciones de elementos y atributos.</span><span class="sxs-lookup"><span data-stu-id="90f1d-123">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="90f1d-124">La capacidad de consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es comparable en cuanto a funcionalidad (aunque no cuanto a sintaxis) a XPath y XQuery.</span><span class="sxs-lookup"><span data-stu-id="90f1d-124">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="90f1d-125">La integración de LINK en C# proporciona una escritura más rápida, comprobación en tiempo de compilación y compatibilidad mejorada con el depurador.</span><span class="sxs-lookup"><span data-stu-id="90f1d-125">The integration of LINQ in C# provides stronger typing, compile-time checking, and improved debugger support.</span></span>

<span data-ttu-id="90f1d-126">Otra ventaja de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la capacidad de usar los resultados de la consulta como parámetros en constructores de objetos <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>, que habilita un método eficaz para crear árboles XML.</span><span class="sxs-lookup"><span data-stu-id="90f1d-126">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="90f1d-127">Este método, denominado *construcción funcional*, permite que los desarrolladores transformen fácilmente árboles XML de una forma a otra.</span><span class="sxs-lookup"><span data-stu-id="90f1d-127">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>

<span data-ttu-id="90f1d-128">Por ejemplo, es posible que tenga un pedido de compra XML típico, como se describe en [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="90f1d-128">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span> <span data-ttu-id="90f1d-129">Mediante [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], podría ejecutar la siguiente consulta para obtener el valor del atributo de número de pieza relativo a cada elemento del pedido de compra:</span><span class="sxs-lookup"><span data-stu-id="90f1d-129">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

<span data-ttu-id="90f1d-130">Esto se puede reescribir con formato de sintaxis de método:</span><span class="sxs-lookup"><span data-stu-id="90f1d-130">This can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

<span data-ttu-id="90f1d-131">A modo de ejemplo, imagine que necesita una lista, ordenada por números de pieza, de los elementos con un valor superior a 100 $.</span><span class="sxs-lookup"><span data-stu-id="90f1d-131">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="90f1d-132">Para obtener esta información, podría ejecutar la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="90f1d-132">To obtain this information, you could run the following query:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

<span data-ttu-id="90f1d-133">De nuevo, esto se puede reescribir con formato de sintaxis de método:</span><span class="sxs-lookup"><span data-stu-id="90f1d-133">Again, this can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

<span data-ttu-id="90f1d-134">Además de estas funcionalidades de LINK, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona una interfaz de programación XML mejorada.</span><span class="sxs-lookup"><span data-stu-id="90f1d-134">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="90f1d-135">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede:</span><span class="sxs-lookup"><span data-stu-id="90f1d-135">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>

- <span data-ttu-id="90f1d-136">Cargar XML a partir de [archivos](how-to-load-xml-from-a-file.md) o [secuencias](how-to-stream-xml-fragments-from-an-xmlreader.md).</span><span class="sxs-lookup"><span data-stu-id="90f1d-136">Load XML from [files](how-to-load-xml-from-a-file.md) or [streams](how-to-stream-xml-fragments-from-an-xmlreader.md).</span></span>

- <span data-ttu-id="90f1d-137">Serializar XML a archivos o secuencias.</span><span class="sxs-lookup"><span data-stu-id="90f1d-137">Serialize XML to files or streams.</span></span>

- <span data-ttu-id="90f1d-138">Crear árboles XML desde cero mediante la construcción funcional.</span><span class="sxs-lookup"><span data-stu-id="90f1d-138">Create XML from scratch by using functional construction.</span></span>

- <span data-ttu-id="90f1d-139">Realizar consultas de XML con ejes de tipo XPath.</span><span class="sxs-lookup"><span data-stu-id="90f1d-139">Query XML using XPath-like axes.</span></span>

- <span data-ttu-id="90f1d-140">Manipular el árbol XML en memoria con métodos como <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> y <xref:System.Xml.Linq.XElement.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="90f1d-140">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>

- <span data-ttu-id="90f1d-141">Validar árboles XML mediante XSD.</span><span class="sxs-lookup"><span data-stu-id="90f1d-141">Validate XML trees using XSD.</span></span>

- <span data-ttu-id="90f1d-142">Usar una combinación de estas características para transformar las formas de los árboles XML.</span><span class="sxs-lookup"><span data-stu-id="90f1d-142">Use a combination of these features to transform XML trees from one shape into another.</span></span>

## <a name="creating-xml-trees"></a><span data-ttu-id="90f1d-143">Crear árboles XML</span><span class="sxs-lookup"><span data-stu-id="90f1d-143">Creating XML Trees</span></span>

<span data-ttu-id="90f1d-144">Una de las ventajas más significativas de la programación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la facilidad con que se pueden crear árboles XML.</span><span class="sxs-lookup"><span data-stu-id="90f1d-144">One of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="90f1d-145">Por ejemplo, para crear un árbol XML pequeño, puede escribir código de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="90f1d-145">For example, to create a small XML tree, you can write code as follows:</span></span>

```csharp
XElement contacts =
new XElement("Contacts",
    new XElement("Contact",
        new XElement("Name", "Patrick Hines"),
        new XElement("Phone", "206-555-0144",
            new XAttribute("Type", "Home")),
        new XElement("phone", "425-555-0145",
            new XAttribute("Type", "Work")),
        new XElement("Address",
            new XElement("Street1", "123 Main St"),
            new XElement("City", "Mercer Island"),
            new XElement("State", "WA"),
            new XElement("Postal", "68042")
        )
    )
);
```

<span data-ttu-id="90f1d-146">Para obtener más información, consulte [Crear árboles XML (C#)](./creating-xml-trees-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="90f1d-146">For more information, see [Creating XML Trees (C#)](./creating-xml-trees-linq-to-xml-2.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="90f1d-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="90f1d-147">See also</span></span>

- [<span data-ttu-id="90f1d-148">Referencia (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="90f1d-148">Reference (LINQ to XML)</span></span>](./reference-linq-to-xml.md)
- [<span data-ttu-id="90f1d-149">LINQ to XML frente a DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="90f1d-149">LINQ to XML vs. DOM (C#)</span></span>](./linq-to-xml-vs-dom.md)
- [<span data-ttu-id="90f1d-150">LINQ to XML frente a otras tecnologías XML</span><span class="sxs-lookup"><span data-stu-id="90f1d-150">LINQ to XML vs. Other XML Technologies</span></span>](./linq-to-xml-vs-other-xml-technologies.md)
- <xref:System.Xml.Linq>
