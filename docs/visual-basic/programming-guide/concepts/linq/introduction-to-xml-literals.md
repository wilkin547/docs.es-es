---
title: Introducción a los literales XML en Visual Basic2
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: 8b92d22727c50274d57a5e407a0ca42807de3a94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397589"
---
# <a name="introduction-to-xml-literals-in-visual-basic"></a><span data-ttu-id="b04a3-102">Introducción a los literales XML de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b04a3-102">Introduction to XML Literals in Visual Basic</span></span>
<span data-ttu-id="b04a3-103">En esta sección se proporciona información sobre cómo crear árboles XML en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b04a3-103">This section provides information about creating XML trees in Visual Basic.</span></span>  
  
 <span data-ttu-id="b04a3-104">Para obtener información sobre el uso de los resultados de las consultas LINQ como contenido para un árbol XML, vea [construcción funcional (LINQ to XML) (Visual Basic)](functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b04a3-104">For information about using the results of LINQ queries as the content for an XML tree, see [Functional Construction (LINQ to XML) (Visual Basic)](functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b04a3-105">Para obtener más información sobre los literales XML en Visual Basic, consulte [información general de LINQ to XML en Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b04a3-105">For more information on XML literals in Visual Basic, see [Overview of LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md).</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="b04a3-106">Crear árboles XML</span><span class="sxs-lookup"><span data-stu-id="b04a3-106">Creating XML Trees</span></span>  
 <span data-ttu-id="b04a3-107">El siguiente ejemplo muestra cómo crear un <xref:System.Xml.Linq.XElement>; en este caso, `contacts`:</span><span class="sxs-lookup"><span data-stu-id="b04a3-107">The following example shows how to create an <xref:System.Xml.Linq.XElement>, in this case `contacts`:</span></span>  
  
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
  
### <a name="creating-an-xelement-with-simple-content"></a><span data-ttu-id="b04a3-108">Crear un XElement con contenido simple</span><span class="sxs-lookup"><span data-stu-id="b04a3-108">Creating an XElement with Simple Content</span></span>  
 <span data-ttu-id="b04a3-109">Puede crear un <xref:System.Xml.Linq.XElement> que incluya un contenido simple, tal y como se detalla a continuación:</span><span class="sxs-lookup"><span data-stu-id="b04a3-109">You can create an <xref:System.Xml.Linq.XElement> that contains simple content, as follows:</span></span>  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)
```  
  
 <span data-ttu-id="b04a3-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b04a3-110">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="b04a3-111">Crear un elemento vacío</span><span class="sxs-lookup"><span data-stu-id="b04a3-111">Creating an Empty Element</span></span>  
 <span data-ttu-id="b04a3-112">Puede crear un <xref:System.Xml.Linq.XElement> vacío, tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b04a3-112">You can create an empty <xref:System.Xml.Linq.XElement>, as follows:</span></span>  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="b04a3-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b04a3-113">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a><span data-ttu-id="b04a3-114">Utilizar expresiones incrustadas</span><span class="sxs-lookup"><span data-stu-id="b04a3-114">Using Embedded Expressions</span></span>  
 <span data-ttu-id="b04a3-115">Una característica importante de los literales XML es que admiten el uso de expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="b04a3-115">An important feature of XML literals is that they allow embedded expressions.</span></span> <span data-ttu-id="b04a3-116">Las expresiones incrustadas le permiten evaluar una expresión e incorporar los resultados de la expresión a un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="b04a3-116">Embedded expressions enable you to evaluate an expression and insert the results of the expression into the XML tree.</span></span> <span data-ttu-id="b04a3-117">Si el resultado de evaluar la expresión es de tipo <xref:System.Xml.Linq.XElement>, se agregará un elemento al árbol.</span><span class="sxs-lookup"><span data-stu-id="b04a3-117">If the expression evaluates to a type of <xref:System.Xml.Linq.XElement>, an element is inserted into the tree.</span></span> <span data-ttu-id="b04a3-118">Si el resultado de evaluar la expresión es de tipo <xref:System.Xml.Linq.XAttribute>, se agregará un atributo al árbol.</span><span class="sxs-lookup"><span data-stu-id="b04a3-118">If the expression evaluates to a type of <xref:System.Xml.Linq.XAttribute>, an attribute is inserted into the tree.</span></span> <span data-ttu-id="b04a3-119">Puede agregar elementos y atributos al árbol solo en aquellos lugares donde sea válido.</span><span class="sxs-lookup"><span data-stu-id="b04a3-119">You can insert elements and attributes into the tree only where they are valid.</span></span>  
  
 <span data-ttu-id="b04a3-120">Es importante reseñar que en una expresión incrustada solo puede aparecer una expresión única.</span><span class="sxs-lookup"><span data-stu-id="b04a3-120">It is important to note that only a single expression can go into an embedded expression.</span></span> <span data-ttu-id="b04a3-121">No es posible incrustar varias instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b04a3-121">You cannot embed multiple statements.</span></span> <span data-ttu-id="b04a3-122">Si una expresión se extiende más allá de una única línea, deberá utilizar el carácter de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="b04a3-122">If an expression extends beyond a single line, you must use the line continuation character.</span></span>  
  
 <span data-ttu-id="b04a3-123">Si utiliza una expresión incrustada para agregar nodos (incluyendo elementos) y atributos ya existentes a nuevo árbol XML y los nodos existentes ya tienen elementos primarios, los nodos se clonarán.</span><span class="sxs-lookup"><span data-stu-id="b04a3-123">If you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree and if the existing nodes are already parented, the nodes are cloned.</span></span> <span data-ttu-id="b04a3-124">Esos nodos clonados nuevos se adjuntan al nuevo árbol XML.</span><span class="sxs-lookup"><span data-stu-id="b04a3-124">The newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="b04a3-125">Si los nodos ya existentes no tienen elementos primarios, los nodos simplemente se adjuntan al nuevo árbol XML.</span><span class="sxs-lookup"><span data-stu-id="b04a3-125">If the existing nodes are not parented, the nodes are simply attached to the new XML tree.</span></span> <span data-ttu-id="b04a3-126">El último ejemplo de este tema muestra este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b04a3-126">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="b04a3-127">El siguiente ejemplo utiliza una expresión incrustada para agregar un elemento al árbol:</span><span class="sxs-lookup"><span data-stu-id="b04a3-127">The following example uses an embedded expression to insert an element into the tree:</span></span>  
  
```vb  
xmlTree1 As XElement = _  
    <Root>  
        <Child>Contents</Child>  
    </Root>  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child> %>  
    </Root>  
Console.WriteLine(xmlTree2)  
```  
  
 <span data-ttu-id="b04a3-128">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b04a3-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a><span data-ttu-id="b04a3-129">Utilizar expresiones incrustadas para el contenido</span><span class="sxs-lookup"><span data-stu-id="b04a3-129">Using Embedded Expressions for Content</span></span>  
 <span data-ttu-id="b04a3-130">Puede utilizar una expresión incrustada para proporcionar el contenido de un elemento:</span><span class="sxs-lookup"><span data-stu-id="b04a3-130">You can use an embedded expression to supply the content of an element:</span></span>  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="b04a3-131">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b04a3-131">This example produces the following output:</span></span>  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a><span data-ttu-id="b04a3-132">Usar una consulta de LINQ en una expresión incrustada</span><span class="sxs-lookup"><span data-stu-id="b04a3-132">Using a LINQ Query in an Embedded Expression</span></span>  
 <span data-ttu-id="b04a3-133">Puede utilizar los resultados proporcionados por una consulta LINQ para el contenido de un elemento:</span><span class="sxs-lookup"><span data-stu-id="b04a3-133">You can use the results of a LINQ query for the content of an element:</span></span>  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="b04a3-134">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b04a3-134">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a><span data-ttu-id="b04a3-135">Utilizar expresiones incrustadas para los nombres de los nodos</span><span class="sxs-lookup"><span data-stu-id="b04a3-135">Using Embedded Expressions for Node Names</span></span>  
 <span data-ttu-id="b04a3-136">También puede utilizar expresiones incrustadas para calcular nombres de atributos, valores de atributos, nombres de elementos y valores de elementos:</span><span class="sxs-lookup"><span data-stu-id="b04a3-136">You can also use embedded expressions to calculate attribute names, attribute values, element names, and element values:</span></span>  
  
```vb  
Dim eleName As String = "ele"  
Dim attName As String = "att"  
Dim attValue As String = "aValue"  
Dim eleValue As String = "eValue"  
Dim n As XElement = _  
    <Root <%= attName %>=<%= attValue %>>  
        <<%= eleName %>>  
            <%= eleValue %>  
        </>  
    </Root>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="b04a3-137">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b04a3-137">This example produces the following output:</span></span>  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a><span data-ttu-id="b04a3-138">Diferencias entre clonación y asociación</span><span class="sxs-lookup"><span data-stu-id="b04a3-138">Cloning vs. Attaching</span></span>  
 <span data-ttu-id="b04a3-139">Como ya se mencionó anteriormente, si utiliza una expresión incrustada para agregar nodos (incluyendo elementos) y atributos ya existentes a nuevo árbol XML y los nodos existentes ya tienen elementos primarios, los nodos se clonarán y esos nuevos nodos clonados se adjuntarán al nuevo árbol XML.</span><span class="sxs-lookup"><span data-stu-id="b04a3-139">As mentioned earlier, if you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree, if the existing nodes are already parented, the nodes are cloned and the newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="b04a3-140">Si los nodos ya existentes no tienen elementos primarios, simplemente se adjuntan al nuevo árbol XML.</span><span class="sxs-lookup"><span data-stu-id="b04a3-140">If the existing nodes are not parented, they are simply attached to the new XML tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="b04a3-141">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b04a3-141">This example produces the following output:</span></span>  
  
```console  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="b04a3-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="b04a3-142">See also</span></span>

- [<span data-ttu-id="b04a3-143">Crear árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b04a3-143">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)
