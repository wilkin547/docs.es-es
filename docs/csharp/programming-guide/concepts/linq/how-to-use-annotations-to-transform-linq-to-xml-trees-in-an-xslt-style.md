---
title: Procedimiento para usar anotaciones para transformar árboles LINQ to XML en un estilo XSLT (C#)
description: Aprenda a usar anotaciones para transformar árboles de LINQ to XML en un estilo XSLT. Vea un ejemplo de transformación de un árbol mediante la función XForm.
ms.date: 07/20/2015
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 844ca08cb2c6b47f7803d388663daeacb65bdb68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302885"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-c"></a><span data-ttu-id="5d89d-104">Procedimiento para usar anotaciones para transformar árboles LINQ to XML en un estilo XSLT (C#)</span><span class="sxs-lookup"><span data-stu-id="5d89d-104">How to use annotations to transform LINQ to XML trees in an XSLT style (C#)</span></span>
<span data-ttu-id="5d89d-105">Se puede usar anotaciones para facilitar transformaciones de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="5d89d-105">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="5d89d-106">Algunos documentos XML están "basados en el documento con contenido mixto".</span><span class="sxs-lookup"><span data-stu-id="5d89d-106">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="5d89d-107">Con estos documentos no se conoce necesariamente la forma de los nodos secundarios de un elemento.</span><span class="sxs-lookup"><span data-stu-id="5d89d-107">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="5d89d-108">Por ejemplo, un nodo que contiene texto puede tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="5d89d-108">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="5d89d-109">Para cualquier nodo de texto dado puede haber cualquier número de elementos secundarios `<b>` y `<i>`.</span><span class="sxs-lookup"><span data-stu-id="5d89d-109">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="5d89d-110">Este enfoque se extiende a otras situaciones diferentes, por ejemplo páginas que contienen diversos elementos secundarios, como párrafos normales, párrafos con viñetas o mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="5d89d-110">This approach extends to a number of other situations, such as pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="5d89d-111">Las celdas de una tabla pueden contener texto, listas desplegables o mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="5d89d-111">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="5d89d-112">Una de las características principal del XML centrado en documentos es que no se sabe qué elemento secundario puede tener cualquier elemento particular.</span><span class="sxs-lookup"><span data-stu-id="5d89d-112">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="5d89d-113">Si desea transformar elementos de un árbol en el que no conoce el elemento secundario de los elementos que desea transformar, entonces este enfoque que usa anotaciones en un enfoque efectivo.</span><span class="sxs-lookup"><span data-stu-id="5d89d-113">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="5d89d-114">El resumen del enfoque es:</span><span class="sxs-lookup"><span data-stu-id="5d89d-114">The summary of the approach is:</span></span>  
  
- <span data-ttu-id="5d89d-115">En primer lugar, anote elementos en el árbol con un elemento de sustitución.</span><span class="sxs-lookup"><span data-stu-id="5d89d-115">First, annotate elements in the tree with a replacement element.</span></span>  
  
- <span data-ttu-id="5d89d-116">En segundo lugar, recorra en iteración todo el árbol, creando un nuevo árbol en el que se reemplaza cada elemento son su anotación.</span><span class="sxs-lookup"><span data-stu-id="5d89d-116">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="5d89d-117">Este ejemplo implementa la iteración y la creación de un nuevo árbol en una función con el nombre `XForm`.</span><span class="sxs-lookup"><span data-stu-id="5d89d-117">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="5d89d-118">En detalle, el enfoque consiste en:</span><span class="sxs-lookup"><span data-stu-id="5d89d-118">In detail, the approach consists of:</span></span>  
  
- <span data-ttu-id="5d89d-119">Ejecutar una o más consultas LINQ to XML que devuelvan el conjunto de elementos que desea transformar de una forma a otra.</span><span class="sxs-lookup"><span data-stu-id="5d89d-119">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="5d89d-120">Para cada elemento de la consulta, agregue un nuevo objeto <xref:System.Xml.Linq.XElement> como anotación al elemento.</span><span class="sxs-lookup"><span data-stu-id="5d89d-120">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="5d89d-121">Este nuevo elemento sustituirá el elemento anotado en el nuevo árbol transformado.</span><span class="sxs-lookup"><span data-stu-id="5d89d-121">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="5d89d-122">Es un código sencillo de escribir, tal como lo demuestra el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5d89d-122">This is simple code to write, as demonstrated by the example.</span></span>  
  
- <span data-ttu-id="5d89d-123">El nuevo elemento que se agrega como anotación puede contener nodos secundarios; puede formar un subárbol con cualquier forma que se desee.</span><span class="sxs-lookup"><span data-stu-id="5d89d-123">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
- <span data-ttu-id="5d89d-124">Existe una regla especial; si un nodo secundario del nuevo elemento está en un espacio de nombres diferente, un espacio de nombres creado con esa finalidad (en este ejemplo, el espacio de nombres es `http://www.microsoft.com/LinqToXmlTransform/2007`), entonces el elemento secundario no se copia al nuevo árbol.</span><span class="sxs-lookup"><span data-stu-id="5d89d-124">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="5d89d-125">En su lugar, si el espacio de nombres es el espacio de nombres especial mencionado anteriormente y el nombre local del elemento es `ApplyTransforms`, los nodos secundarios del elemento del árbol de origen se recorren en iteración y se copian al nuevo árbol (con la excepción que los elementos secundarios anotados se transforman de acuerdo con esas reglas).</span><span class="sxs-lookup"><span data-stu-id="5d89d-125">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
- <span data-ttu-id="5d89d-126">Esto es parecido a la especificación de transformaciones en XSL.</span><span class="sxs-lookup"><span data-stu-id="5d89d-126">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="5d89d-127">La consulta que selecciona un conjunto de nodos es análoga a la expresión XPath para una plantilla.</span><span class="sxs-lookup"><span data-stu-id="5d89d-127">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="5d89d-128">El código para crear el nuevo <xref:System.Xml.Linq.XElement> que se guarda como anotación es análogo al constructor de secuencias en XSL y el elemento `ApplyTransforms` es análogo en función al elemento `xsl:apply-templates` en XSL.</span><span class="sxs-lookup"><span data-stu-id="5d89d-128">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
- <span data-ttu-id="5d89d-129">Una ventaja de este enfoque es que al formular consultas siempre se escriben consultas en el árbol de origen sin modificar.</span><span class="sxs-lookup"><span data-stu-id="5d89d-129">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="5d89d-130">No hay que preocuparse de cómo afectan a las consultas que se están escribiendo las modificaciones del árbol.</span><span class="sxs-lookup"><span data-stu-id="5d89d-130">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="5d89d-131">Transformar un árbol</span><span class="sxs-lookup"><span data-stu-id="5d89d-131">Transforming a Tree</span></span>  
 <span data-ttu-id="5d89d-132">El primer ejemplo cambia el nombre de todos los nodos `Paragraph` a `para`.</span><span class="sxs-lookup"><span data-stu-id="5d89d-132">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement root = XElement.Parse(@"  
<Root>  
    <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
    <Paragraph>More text.</Paragraph>  
</Root>");  
  
// replace Paragraph with para  
foreach (var el in root.Descendants("Paragraph"))  
    el.AddAnnotation(  
        new XElement("para",  
            // same idea as xsl:apply-templates  
            new XElement(xf + "ApplyTransforms")  
        )  
    );  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newRoot = XForm(root);  
  
Console.WriteLine(newRoot);  
```  
  
 <span data-ttu-id="5d89d-133">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5d89d-133">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="5d89d-134">Una transformación más complicada</span><span class="sxs-lookup"><span data-stu-id="5d89d-134">A More Complicated Transform</span></span>  
 <span data-ttu-id="5d89d-135">El siguiente ejemplo consulta el árbol y calcula la media y la suma de los elementos `Data` y los agrega como nuevos elementos al árbol.</span><span class="sxs-lookup"><span data-stu-id="5d89d-135">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement data = new XElement("Root",  
    new XElement("Data", 20),  
    new XElement("Data", 10),  
    new XElement("Data", 3)  
);  
  
// while adding annotations, you can query the source tree all you want,  
// as the tree is not mutated while annotating.
var avg = data.Elements("Data").Select(z => (Decimal)z).Average();
data.AddAnnotation(  
    new XElement("Root",  
        new XElement(xf + "ApplyTransforms"),  
        new XElement("Average", $"{avg:F4}"),
        new XElement("Sum",  
            data  
            .Elements("Data")  
            .Select(z => (int)z)  
            .Sum()  
        )  
    )  
);  
  
Console.WriteLine("Before Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(data);  
Console.WriteLine();  
Console.WriteLine();  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newData = XForm(data);  
  
Console.WriteLine("After Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="5d89d-136">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5d89d-136">This example produces the following output:</span></span>  
  
```output  
Before Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
</Root>  
  
After Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
  <Average>11.0000</Average>  
  <Sum>33</Sum>  
</Root>  
```  
  
## <a name="effecting-the-transform"></a><span data-ttu-id="5d89d-137">Llevar a cabo la transformación</span><span class="sxs-lookup"><span data-stu-id="5d89d-137">Effecting the Transform</span></span>  
 <span data-ttu-id="5d89d-138">Una pequeña función, `XForm`, crea un nuevo árbol transformado a partir del árbol original anotado.</span><span class="sxs-lookup"><span data-stu-id="5d89d-138">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
- <span data-ttu-id="5d89d-139">El pseudocódigo para la función es bastante sencillo:</span><span class="sxs-lookup"><span data-stu-id="5d89d-139">The pseudo code for the function is quite simple:</span></span>  
  
```text  
The function takes an XElement as an argument and returns an XElement.
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="5d89d-140">A continuación se muestra la implementación de esta función:</span><span class="sxs-lookup"><span data-stu-id="5d89d-140">Following is the implementation of this function:</span></span>  
  
```csharp  
// Build a transformed XML tree per the annotations  
static XElement XForm(XElement source)  
{  
    XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    XName at = xf + "ApplyTransforms";  
  
    if (source.Annotation<XElement>() != null)  
    {  
        XElement anno = source.Annotation<XElement>();  
        return new XElement(anno.Name,  
            anno.Attributes(),  
            anno  
            .Nodes()  
            .Select(  
                (XNode n) =>  
                {  
                    XElement annoEl = n as XElement;  
                    if (annoEl != null)  
                    {  
                        if (annoEl.Name == at)  
                            return (object)(  
                                source.Nodes()  
                                .Select(  
                                    (XNode n2) =>  
                                    {  
                                        XElement e2 = n2 as XElement;  
                                        if (e2 == null)  
                                            return n2;  
                                        else  
                                            return XForm(e2);  
                                    }  
                                )  
                            );  
                        else  
                            return n;  
                    }  
                    else  
                        return n;  
                }  
            )  
        );  
    }  
    else  
    {  
        return new XElement(source.Name,  
            source.Attributes(),  
            source  
                .Nodes()  
                .Select(n =>  
                {  
                    XElement el = n as XElement;  
                    if (el == null)  
                        return n;  
                    else  
                        return XForm(el);  
                }  
                )  
        );  
    }  
}
```  
  
## <a name="complete-example"></a><span data-ttu-id="5d89d-141">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="5d89d-141">Complete Example</span></span>  
 <span data-ttu-id="5d89d-142">El siguiente código es un ejemplo completo que incluye la función `XForm`.</span><span class="sxs-lookup"><span data-stu-id="5d89d-142">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="5d89d-143">Incluye unos pocos usos típicos de este tipo de transformación:</span><span class="sxs-lookup"><span data-stu-id="5d89d-143">It includes a few of the typical uses of this type of transform:</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Xml;  
using System.Xml.Linq;  
  
class Program  
{  
    static XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    static XName at = xf + "ApplyTransforms";  
  
    // Build a transformed XML tree per the annotations  
    static XElement XForm(XElement source)  
    {  
        if (source.Annotation<XElement>() != null)  
        {  
            XElement anno = source.Annotation<XElement>();  
            return new XElement(anno.Name,  
                anno.Attributes(),  
                anno  
                .Nodes()  
                .Select(  
                    (XNode n) =>  
                    {  
                        XElement annoEl = n as XElement;  
                        if (annoEl != null)  
                        {  
                            if (annoEl.Name == at)  
                                return (object)(  
                                    source.Nodes()  
                                    .Select(  
                                        (XNode n2) =>  
                                        {  
                                            XElement e2 = n2 as XElement;  
                                            if (e2 == null)  
                                                return n2;  
                                            else  
                                                return XForm(e2);  
                                        }  
                                    )  
                                );  
                            else  
                                return n;  
                        }  
                        else  
                            return n;  
                    }  
                )  
            );  
        }  
        else  
        {  
            return new XElement(source.Name,  
                source.Attributes(),  
                source  
                    .Nodes()  
                    .Select(n =>  
                    {  
                        XElement el = n as XElement;  
                        if (el == null)  
                            return n;  
                        else  
                            return XForm(el);  
                    }  
                    )  
            );  
        }  
    }  
  
    static void Main(string[] args)  
    {  
        XElement root = new XElement("Root",  
            new XComment("A comment"),  
            new XAttribute("Att1", 123),  
            new XElement("Child", 1),  
            new XElement("Child", 2),  
            new XElement("Other",  
                new XElement("GC", 3),  
                new XElement("GC", 4)  
            ),  
            XElement.Parse(  
              "<SomeMixedContent>This is <i>an</i> element that " +  
              "<b>has</b> some mixed content</SomeMixedContent>"),  
            new XElement("AnUnchangedElement", 42)  
        );  
  
        // each of the following serves the same semantic purpose as  
        // XSLT templates and sequence constructors  
  
        // replace Child with NewChild  
        foreach (var el in root.Elements("Child"))  
            el.AddAnnotation(new XElement("NewChild", (string)el));  
  
        // replace first GC with GrandChild, add an attribute  
        foreach (var el in root.Descendants("GC").Take(1))  
            el.AddAnnotation(  
                new XElement("GrandChild",  
                    new XAttribute("ANewAttribute", 999),  
                    (string)el  
                )  
            );  
  
        // replace Other with NewOther, add new child elements around original content  
        foreach (var el in root.Elements("Other"))  
            el.AddAnnotation(  
                new XElement("NewOther",  
                    new XElement("MyNewChild", 1),  
                    // same idea as xsl:apply-templates  
                    new XElement(xf + "ApplyTransforms"),  
                    new XElement("ChildThatComesAfter")  
                )  
            );  
  
        // change name of element that has mixed content  
        root.Descendants("SomeMixedContent").First().AddAnnotation(  
            new XElement("MixedContent",  
                new XElement(xf + "ApplyTransforms")  
            )  
        );  
  
        // replace <b> with <Bold>  
        foreach (var el in root.Descendants("b"))  
            el.AddAnnotation(  
                new XElement("Bold",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        // replace <i> with <Italic>  
        foreach (var el in root.Descendants("i"))  
            el.AddAnnotation(  
                new XElement("Italic",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        Console.WriteLine("Before Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(root);  
        Console.WriteLine();  
        Console.WriteLine();  
        XElement newRoot = XForm(root);  
  
        Console.WriteLine("After Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(newRoot);  
    }  
}  
```  
  
 <span data-ttu-id="5d89d-144">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5d89d-144">This example produces the following output:</span></span>  
  
```output  
Before Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <Child>1</Child>  
  <Child>2</Child>  
  <Other>  
    <GC>3</GC>  
    <GC>4</GC>  
  </Other>  
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
After Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <NewChild>1</NewChild>  
  <NewChild>2</NewChild>  
  <NewOther>  
    <MyNewChild>1</MyNewChild>  
    <GrandChild ANewAttribute="999">3</GrandChild>  
    <GC>4</GC>  
    <ChildThatComesAfter />  
  </NewOther>  
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
```  
  