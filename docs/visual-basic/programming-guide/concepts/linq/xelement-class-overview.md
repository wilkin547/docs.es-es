---
title: "Información general de la clase XElement (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: decd7c4f805de0d23b091972ee95a323baf0b7d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="8f16b-102">Información general de la clase XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f16b-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="8f16b-103">La clase <xref:System.Xml.Linq.XElement> es una de las clases fundamentales de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f16b-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="8f16b-104">Representa a un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8f16b-104">It represents an XML element.</span></span> <span data-ttu-id="8f16b-105">Puede utilizar esta clase para crear elementos; cambiar el contenido del elemento; agregar, modificar o eliminar elementos secundarios; agregar atributos a un elemento; o serializar el contenido de un elemento en forma de texto.</span><span class="sxs-lookup"><span data-stu-id="8f16b-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="8f16b-106">También puede operar con otras clases de <xref:System.Xml?displayProperty=nameWithType>, como son <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="8f16b-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="8f16b-107">Funcionalidad de XElement</span><span class="sxs-lookup"><span data-stu-id="8f16b-107">XElement Functionality</span></span>  
 <span data-ttu-id="8f16b-108">Este tema describe la funcionalidad que ofrece la clase <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8f16b-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="8f16b-109">Construir árboles XML</span><span class="sxs-lookup"><span data-stu-id="8f16b-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="8f16b-110">Es posible construir árboles XML de diferentes formas, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f16b-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
-   <span data-ttu-id="8f16b-111">Puede construir un árbol XML mediante código.</span><span class="sxs-lookup"><span data-stu-id="8f16b-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="8f16b-112">Para obtener más información, consulte [crear árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="8f16b-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
-   <span data-ttu-id="8f16b-113">Puede analizar XML a partir de diferentes orígenes, incluyendo un <xref:System.IO.TextReader>, archivos de texto o direcciones web (URL).</span><span class="sxs-lookup"><span data-stu-id="8f16b-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="8f16b-114">Para obtener más información, consulte [analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8f16b-114">For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
-   <span data-ttu-id="8f16b-115">También puede utilizar un <xref:System.Xml.XmlReader> para rellenar el árbol.</span><span class="sxs-lookup"><span data-stu-id="8f16b-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="8f16b-116">Para obtener más información, consulta <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f16b-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
-   <span data-ttu-id="8f16b-117">Si dispone de un módulo que pueda escribir contenidos en un <xref:System.Xml.XmlWriter>, puede utilizar el método <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear un sistema de escritura, para pasar éste al módulo y para utilizar después el contenido que se haya escrito en <xref:System.Xml.XmlWriter> para rellenar el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="8f16b-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="8f16b-118">No obstante, la forma más habitual de crear un árbol XML es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f16b-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="8f16b-119">Otra técnica usada con frecuencia para crear un árbol XML implica el uso de los resultados de una consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] para rellenar el árbol XML, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f16b-119">Another very common technique for creating an XML tree involves using the results of a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to populate an XML tree, as shown in the following example:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="8f16b-120">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8f16b-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="8f16b-121">Serializar árboles XML</span><span class="sxs-lookup"><span data-stu-id="8f16b-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="8f16b-122">Puede serializar un árbol XML en un <xref:System.IO.File>, un <xref:System.IO.TextWriter> o en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8f16b-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="8f16b-123">Para obtener más información, consulte [serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="8f16b-123">For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="8f16b-124">Recuperar datos XML mediante los métodos de los ejes</span><span class="sxs-lookup"><span data-stu-id="8f16b-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="8f16b-125">Puede utilizar los métodos de los ejes para recuperar atributos, elementos secundarios, elementos descendientes y elementos antecesores.</span><span class="sxs-lookup"><span data-stu-id="8f16b-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="8f16b-126">Las consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] utilizan los métodos de los ejes y proporcionan numerosos mecanismos, flexibles y potentes, para recorrer y procesar árboles XML.</span><span class="sxs-lookup"><span data-stu-id="8f16b-126">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="8f16b-127">Para obtener más información, consulte [ejes LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span><span class="sxs-lookup"><span data-stu-id="8f16b-127">For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="8f16b-128">Consultar árboles XML</span><span class="sxs-lookup"><span data-stu-id="8f16b-128">Querying XML Trees</span></span>  
 <span data-ttu-id="8f16b-129">Puede escribir consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] que extraigan datos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="8f16b-129">You can write [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="8f16b-130">Para obtener más información, consulte [consultar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="8f16b-130">For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="8f16b-131">Modificar árboles XML</span><span class="sxs-lookup"><span data-stu-id="8f16b-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="8f16b-132">Puede modificar un elemento de diferentes maneras, incluyendo el cambiar su contenido o sus atributos.</span><span class="sxs-lookup"><span data-stu-id="8f16b-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="8f16b-133">También puede eliminar un elemento dependiente de un elemento primario.</span><span class="sxs-lookup"><span data-stu-id="8f16b-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="8f16b-134">Para obtener más información, consulte [Modificar árboles XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8f16b-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f16b-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f16b-135">See Also</span></span>  
 [<span data-ttu-id="8f16b-136">LINQ to XML de información general de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f16b-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
