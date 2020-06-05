---
title: Información general de LINQ to XML
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: afdec54ac05bb4a631de7fdb599123ffe964c443
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368744"
---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="9119a-102">Información general sobre LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9119a-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="9119a-103">XML se ha adoptado ampliamente como un modo de dar formato a datos en diversos contextos.</span><span class="sxs-lookup"><span data-stu-id="9119a-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="9119a-104">Por ejemplo, puede encontrar XML en la web, en archivos de configuración, en archivos de Microsoft Office Word y en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="9119a-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="9119a-105">es un método actualizado y rediseñado para la programación con XML.</span><span class="sxs-lookup"><span data-stu-id="9119a-105">is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="9119a-106">Proporciona capacidades de modificación de documentos en memoria del Document Object Model (DOM) y admite expresiones de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="9119a-106">It provides the in-memory document-modification capabilities of the Document Object Model (DOM) and supports LINQ query expressions.</span></span> <span data-ttu-id="9119a-107">Aunque estas expresiones de consulta difieren sintácticamente de XPath, proporcionan una funcionalidad similar.</span><span class="sxs-lookup"><span data-stu-id="9119a-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="9119a-108">Desarrolladores de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="9119a-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="9119a-109">se dirige a diversos desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="9119a-109">targets a variety of developers.</span></span> <span data-ttu-id="9119a-110">Para el desarrollador medio que solo desea completar una tarea, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica el código XML al proporcionar una experiencia de consulta similar a SQL.</span><span class="sxs-lookup"><span data-stu-id="9119a-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="9119a-111">Con un poco de estudio, los programadores pueden aprender a escribir consultas sucintas y eficaces en el lenguaje de programación que prefieran.</span><span class="sxs-lookup"><span data-stu-id="9119a-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="9119a-112">Los desarrolladores profesionales pueden usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para aumentar considerablemente su productividad.</span><span class="sxs-lookup"><span data-stu-id="9119a-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="9119a-113">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], pueden escribir menos código, que a su vez resulte más expresivo, compacto y eficaz.</span><span class="sxs-lookup"><span data-stu-id="9119a-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="9119a-114">Pueden usar expresiones de consulta de distintos dominios de datos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="9119a-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="9119a-115">¿Qué es LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="9119a-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="9119a-116">es una interfaz de programación XML en memoria y habilitada para LINQ que permite trabajar con XML desde los lenguajes de programación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9119a-116">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET Framework programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="9119a-117">se parece a Document Object Model (DOM) en lo que respecta a la inserción del documento XML en la memoria.</span><span class="sxs-lookup"><span data-stu-id="9119a-117">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="9119a-118">Puede consultar y modificar el documento; una vez modificado, puede guardarlo en un archivo o serializarlo y enviarlo a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="9119a-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="9119a-119">Sin embargo, es [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] diferente de Dom: proporciona un nuevo modelo de objetos que es más ligero y más fácil de trabajar con, y que aprovecha las características de lenguaje de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9119a-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="9119a-120">La ventaja más importante de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es su integración con Language-Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="9119a-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="9119a-121">Esta integración permite escribir consultas en el documento XML en memoria para recuperar colecciones de elementos y atributos.</span><span class="sxs-lookup"><span data-stu-id="9119a-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="9119a-122">La capacidad de consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es comparable en cuanto a funcionalidad (aunque no cuanto a sintaxis) a XPath y XQuery.</span><span class="sxs-lookup"><span data-stu-id="9119a-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="9119a-123">La integración de LINQ en Visual Basic proporciona tipos más seguros, comprobaciones en tiempo de compilación y compatibilidad mejorada con el depurador.</span><span class="sxs-lookup"><span data-stu-id="9119a-123">The integration of LINQ in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="9119a-124">Otra ventaja de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la capacidad de usar los resultados de la consulta como parámetros en constructores de objetos <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>, que habilita un método eficaz para crear árboles XML.</span><span class="sxs-lookup"><span data-stu-id="9119a-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="9119a-125">Este método, denominado *construcción funcional*, permite que los desarrolladores transformen fácilmente árboles XML de una forma a otra.</span><span class="sxs-lookup"><span data-stu-id="9119a-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="9119a-126">Por ejemplo, podría tener un pedido de compra XML común, como el que se describe en [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).</span><span class="sxs-lookup"><span data-stu-id="9119a-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span> <span data-ttu-id="9119a-127">Mediante [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], podría ejecutar la siguiente consulta para obtener el valor del atributo de número de pieza relativo a cada elemento del pedido de compra:</span><span class="sxs-lookup"><span data-stu-id="9119a-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="9119a-128">A modo de ejemplo, imagine que necesita una lista, ordenada por números de pieza, de los elementos con un valor superior a 100 $.</span><span class="sxs-lookup"><span data-stu-id="9119a-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="9119a-129">Para obtener esta información, podría ejecutar la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="9119a-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="9119a-130">Además de estas funcionalidades de LINK, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona una interfaz de programación XML mejorada.</span><span class="sxs-lookup"><span data-stu-id="9119a-130">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="9119a-131">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede:</span><span class="sxs-lookup"><span data-stu-id="9119a-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
- <span data-ttu-id="9119a-132">Cargar XML a partir de archivos o secuencias.</span><span class="sxs-lookup"><span data-stu-id="9119a-132">Load XML from files or streams.</span></span>  
  
- <span data-ttu-id="9119a-133">Serializar XML a archivos o secuencias.</span><span class="sxs-lookup"><span data-stu-id="9119a-133">Serialize XML to files or streams.</span></span>  
  
- <span data-ttu-id="9119a-134">Crear árboles XML desde cero mediante la construcción funcional.</span><span class="sxs-lookup"><span data-stu-id="9119a-134">Create XML from scratch by using functional construction.</span></span>  
  
- <span data-ttu-id="9119a-135">Realizar consultas de XML con ejes de tipo XPath.</span><span class="sxs-lookup"><span data-stu-id="9119a-135">Query XML using XPath-like axes.</span></span>  
  
- <span data-ttu-id="9119a-136">Manipular el árbol XML en memoria con métodos como <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> y <xref:System.Xml.Linq.XElement.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="9119a-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
- <span data-ttu-id="9119a-137">Validar árboles XML mediante XSD.</span><span class="sxs-lookup"><span data-stu-id="9119a-137">Validate XML trees using XSD.</span></span>  
  
- <span data-ttu-id="9119a-138">Usar una combinación de estas características para transformar las formas de los árboles XML.</span><span class="sxs-lookup"><span data-stu-id="9119a-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="9119a-139">Crear árboles XML</span><span class="sxs-lookup"><span data-stu-id="9119a-139">Creating XML Trees</span></span>  
 <span data-ttu-id="9119a-140">Una de la ventajas más significativas de la programación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la facilidad con que se pueden crear árboles XML.</span><span class="sxs-lookup"><span data-stu-id="9119a-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="9119a-141">Por ejemplo, para crear un árbol XML pequeño, puede escribir código como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="9119a-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 <span data-ttu-id="9119a-142">El compilador de Visual Basic traduce los literales XML en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="9119a-142">The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.</span></span>  
  
 <span data-ttu-id="9119a-143">Para obtener más información, vea [crear árboles XML (Visual Basic)](creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="9119a-143">For more information, see [Creating XML Trees (Visual Basic)](creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9119a-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9119a-144">See also</span></span>

- <xref:System.Xml.Linq>
- [<span data-ttu-id="9119a-145">Introducción (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="9119a-145">Getting Started (LINQ to XML)</span></span>](getting-started-linq-to-xml.md)
- [<span data-ttu-id="9119a-146">Información general sobre LINQ to XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9119a-146">Overview of LINQ to XML in Visual Basic</span></span>](../../language-features/xml/overview-of-linq-to-xml.md)
- [<span data-ttu-id="9119a-147">XML</span><span class="sxs-lookup"><span data-stu-id="9119a-147">XML</span></span>](../../language-features/xml/index.md)
