---
title: Información general de LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: 318c5494134fd1dd3ac2adbf538d693ad4a5dbf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339386"
---
# <a name="linq-to-xml-overview-c"></a><span data-ttu-id="eef22-102">Información general de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="eef22-102">LINQ to XML Overview (C#)</span></span>
<span data-ttu-id="eef22-103">XML se ha adoptado ampliamente como un modo de dar formato a datos en diversos contextos.</span><span class="sxs-lookup"><span data-stu-id="eef22-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="eef22-104">Por ejemplo, puede encontrar XML en la web, en archivos de configuración, en archivos de Microsoft Office Word y en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="eef22-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="eef22-105"> es un método actualizado y rediseñado para la programación con XML.</span><span class="sxs-lookup"><span data-stu-id="eef22-105"> is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="eef22-106">Proporciona capacidades de modificación de documento en memoria de Document Object Model (DOM), y es compatible con expresiones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eef22-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="eef22-107">Aunque estas expresiones de consulta difieren sintácticamente de XPath, proporcionan una funcionalidad similar.</span><span class="sxs-lookup"><span data-stu-id="eef22-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="eef22-108">Desarrolladores de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="eef22-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="eef22-109"> se dirige a diversos desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="eef22-109"> targets a variety of developers.</span></span> <span data-ttu-id="eef22-110">Para el desarrollador medio que solo desea completar una tarea, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica el código XML al proporcionar una experiencia de consulta similar a SQL.</span><span class="sxs-lookup"><span data-stu-id="eef22-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="eef22-111">Con un poco de estudio, los programadores pueden aprender a escribir consultas sucintas y eficaces en el lenguaje de programación que prefieran.</span><span class="sxs-lookup"><span data-stu-id="eef22-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="eef22-112">Los desarrolladores profesionales pueden usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para aumentar considerablemente su productividad.</span><span class="sxs-lookup"><span data-stu-id="eef22-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="eef22-113">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], pueden escribir menos código, que a su vez resulte más expresivo, compacto y eficaz.</span><span class="sxs-lookup"><span data-stu-id="eef22-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="eef22-114">Pueden usar expresiones de consulta de distintos dominios de datos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="eef22-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="eef22-115">¿Qué es LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="eef22-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="eef22-116"> es una interfaz de programación XML en memoria y habilitada para LINQ que permite trabajar con XML desde los lenguajes de programación de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eef22-116"> is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="eef22-117"> se parece a Document Object Model (DOM) en lo que respecta a la inserción del documento XML en la memoria.</span><span class="sxs-lookup"><span data-stu-id="eef22-117"> is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="eef22-118">Puede consultar y modificar el documento; una vez modificado, puede guardarlo en un archivo o serializarlo y enviarlo a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="eef22-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="eef22-119">En cambio, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es diferente de DOM: proporciona un nuevo modelo de objetos más ligero, con el que se trabaja más fácilmente y que aprovecha las características de lenguaje de C#.</span><span class="sxs-lookup"><span data-stu-id="eef22-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in C#.</span></span>  
  
 <span data-ttu-id="eef22-120">La ventaja más importante de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] radica en su integración con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eef22-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span></span> <span data-ttu-id="eef22-121">Esta integración permite escribir consultas en el documento XML en memoria para recuperar colecciones de elementos y atributos.</span><span class="sxs-lookup"><span data-stu-id="eef22-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="eef22-122">La capacidad de consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es comparable en cuanto a funcionalidad (aunque no cuanto a sintaxis) a XPath y XQuery.</span><span class="sxs-lookup"><span data-stu-id="eef22-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="eef22-123">La integración de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] en C# proporciona una escritura más rápida, comprobación en tiempo de compilación y una compatibilidad mejorada con el depurador.</span><span class="sxs-lookup"><span data-stu-id="eef22-123">The integration of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in C# provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="eef22-124">Otra ventaja de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la capacidad de usar los resultados de la consulta como parámetros en constructores de objetos <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>, que habilita un método eficaz para crear árboles XML.</span><span class="sxs-lookup"><span data-stu-id="eef22-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="eef22-125">Este método, denominado *construcción funcional*, permite que los desarrolladores transformen fácilmente árboles XML de una forma a otra.</span><span class="sxs-lookup"><span data-stu-id="eef22-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="eef22-126">Por ejemplo, podría tener un pedido de compra XML común, como el que se describe en [Sample XML File: Typical Purchase Order (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]).</span><span class="sxs-lookup"><span data-stu-id="eef22-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span></span> <span data-ttu-id="eef22-127">Mediante [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], podría ejecutar la siguiente consulta para obtener el valor del atributo de número de pieza relativo a cada elemento del pedido de compra:</span><span class="sxs-lookup"><span data-stu-id="eef22-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```csharp  
IEnumerable<string> partNos =  
from item in purchaseOrder.Descendants("Item")  
select (string) item.Attribute("PartNumber");  
```  
  
 <span data-ttu-id="eef22-128">A modo de ejemplo, imagine que necesita una lista, ordenada por números de pieza, de los elementos con un valor superior a 100 $.</span><span class="sxs-lookup"><span data-stu-id="eef22-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="eef22-129">Para obtener esta información, podría ejecutar la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="eef22-129">To obtain this information, you could run the following query:</span></span>  
  
```csharp  
IEnumerable<XElement> partNos =  
from item in purchaseOrder.Descendants("Item")  
where (int) item.Element("Quantity") *  
    (decimal) item.Element("USPrice") > 100  
orderby (string)item.Element("PartNumber")  
select item;  
```  
  
 <span data-ttu-id="eef22-130">Además de estas capacidades de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona una interfaz de programación XML mejorada.</span><span class="sxs-lookup"><span data-stu-id="eef22-130">In addition to these [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="eef22-131">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede:</span><span class="sxs-lookup"><span data-stu-id="eef22-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="eef22-132">Cargar XML a partir de archivos o secuencias.</span><span class="sxs-lookup"><span data-stu-id="eef22-132">Load XML from files or streams.</span></span>  
  
-   <span data-ttu-id="eef22-133">Serializar XML a archivos o secuencias.</span><span class="sxs-lookup"><span data-stu-id="eef22-133">Serialize XML to files or streams.</span></span>  
  
-   <span data-ttu-id="eef22-134">Crear árboles XML desde cero mediante la construcción funcional.</span><span class="sxs-lookup"><span data-stu-id="eef22-134">Create XML from scratch by using functional construction.</span></span>  
  
-   <span data-ttu-id="eef22-135">Realizar consultas de XML con ejes de tipo XPath.</span><span class="sxs-lookup"><span data-stu-id="eef22-135">Query XML using XPath-like axes.</span></span>  
  
-   <span data-ttu-id="eef22-136">Manipular el árbol XML en memoria con métodos como <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> y <xref:System.Xml.Linq.XElement.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="eef22-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
-   <span data-ttu-id="eef22-137">Validar árboles XML mediante XSD.</span><span class="sxs-lookup"><span data-stu-id="eef22-137">Validate XML trees using XSD.</span></span>  
  
-   <span data-ttu-id="eef22-138">Usar una combinación de estas características para transformar las formas de los árboles XML.</span><span class="sxs-lookup"><span data-stu-id="eef22-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="eef22-139">Crear árboles XML</span><span class="sxs-lookup"><span data-stu-id="eef22-139">Creating XML Trees</span></span>  
 <span data-ttu-id="eef22-140">Una de las ventajas más significativas de la programación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la facilidad con que se pueden crear árboles XML.</span><span class="sxs-lookup"><span data-stu-id="eef22-140">One of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="eef22-141">Por ejemplo, para crear un árbol XML pequeño, puede escribir código de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="eef22-141">For example, to create a small XML tree, you can write code as follows:</span></span>  
  
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
  
 <span data-ttu-id="eef22-142">Para obtener más información, consulte [Crear árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="eef22-142">For more information, see [Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef22-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="eef22-143">See Also</span></span>  
 <xref:System.Xml.Linq>  
 [<span data-ttu-id="eef22-144">Introducción (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="eef22-144">Getting Started (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
