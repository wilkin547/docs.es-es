---
title: Asignar la jerarquía de objetos a datos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
ms.openlocfilehash: 4ad505749625e22a09406549329179990b81c140
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794395"
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="29587-102">Asignar la jerarquía de objetos a datos XML</span><span class="sxs-lookup"><span data-stu-id="29587-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="29587-103">Cuando un documento XML está en la memoria, la representación conceptual es un árbol.</span><span class="sxs-lookup"><span data-stu-id="29587-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="29587-104">Al programar, hay una jerarquía de objetos para tener acceso a los nodos del árbol.</span><span class="sxs-lookup"><span data-stu-id="29587-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="29587-105">En el ejemplo siguiente se muestra cómo se convierte el contenido XML en nodos.</span><span class="sxs-lookup"><span data-stu-id="29587-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="29587-106">A medida que el contenido XML se lee en el modelo de objetos de documento (DOM), las partes se traducen en nodos, que mantienen metadatos adicionales acerca de sí mismos, como su tipo y valores.</span><span class="sxs-lookup"><span data-stu-id="29587-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="29587-107">El tipo de nodo es su objeto y es lo que determina qué acciones pueden realizarse y qué propiedades pueden establecerse o recuperarse.</span><span class="sxs-lookup"><span data-stu-id="29587-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="29587-108">Si tiene el siguiente contenido XML simple:</span><span class="sxs-lookup"><span data-stu-id="29587-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="29587-109">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="29587-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="29587-110">La entrada se representa en la memoria como el siguiente árbol de nodos con la propiedad de tipo de nodo asignada:</span><span class="sxs-lookup"><span data-stu-id="29587-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="29587-111">![Ejemplo de árbol de nodos](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="29587-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="29587-112">Representación de árbol de nodo de libro y título</span><span class="sxs-lookup"><span data-stu-id="29587-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="29587-113">El elemento `book` se convierte en un objeto **XmlElement**, el siguiente elemento, `title`, también se convierte en un objeto **XmlElement**, mientras que el contenido del elemento se convierte en un objeto **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="29587-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="29587-114">Al observar los métodos y las propiedades del objeto **XmlElement**, estos difieren de los disponibles en un objeto **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="29587-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="29587-115">Por tanto, es fundamental saber en qué tipo de nodo se convierte el marcado XML, puesto que determina las acciones que se pueden realizar.</span><span class="sxs-lookup"><span data-stu-id="29587-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="29587-116">En el ejemplo siguiente se leen datos XML y se escribe texto diferente, en función del tipo de nodo.</span><span class="sxs-lookup"><span data-stu-id="29587-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="29587-117">Se usa el siguiente archivo de datos XML como entrada, **items.xml**:</span><span class="sxs-lookup"><span data-stu-id="29587-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="29587-118">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="29587-118">**Input**</span></span>  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 <span data-ttu-id="29587-119">En el ejemplo de código siguiente se lee el archivo **items.xml** y se presenta información para cada tipo de nodo.</span><span class="sxs-lookup"><span data-stu-id="29587-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and
            'ignore all white space nodes.
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 <span data-ttu-id="29587-120">La salida del ejemplo revela la asignación de los datos a los tipos de nodo.</span><span class="sxs-lookup"><span data-stu-id="29587-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="29587-121">**Salida**</span><span class="sxs-lookup"><span data-stu-id="29587-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>
```  
  
 <span data-ttu-id="29587-122">Si se toma una línea de la entrada cada vez y se utiliza la salida generada por el código, se puede utilizar la tabla siguiente para analizar qué prueba de nodo genera qué línea de salida y, por tanto, se puede comprender en qué tipo de nodo se convierten los datos XML.</span><span class="sxs-lookup"><span data-stu-id="29587-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="29587-123">Entrada</span><span class="sxs-lookup"><span data-stu-id="29587-123">Input</span></span>|<span data-ttu-id="29587-124">Salida</span><span class="sxs-lookup"><span data-stu-id="29587-124">Output</span></span>|<span data-ttu-id="29587-125">Prueba de tipo de nodo</span><span class="sxs-lookup"><span data-stu-id="29587-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="29587-126">\<?xml version="1.0"?></span><span class="sxs-lookup"><span data-stu-id="29587-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="29587-127">\<?xml version='1.0'?></span><span class="sxs-lookup"><span data-stu-id="29587-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="29587-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="29587-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="29587-129">\<!-- Este es un ejemplo de documento XML --></span><span class="sxs-lookup"><span data-stu-id="29587-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="29587-130">\<!--Este es un ejemplo de documento XML --></span><span class="sxs-lookup"><span data-stu-id="29587-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="29587-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="29587-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="29587-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span><span class="sxs-lookup"><span data-stu-id="29587-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="29587-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span><span class="sxs-lookup"><span data-stu-id="29587-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="29587-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="29587-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="29587-135">\<Items></span><span class="sxs-lookup"><span data-stu-id="29587-135">\<Items></span></span>|<span data-ttu-id="29587-136">\<Items></span><span class="sxs-lookup"><span data-stu-id="29587-136">\<Items></span></span>|<span data-ttu-id="29587-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="29587-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="29587-138">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-138">\<Item></span></span>|<span data-ttu-id="29587-139">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-139">\<Item></span></span>|<span data-ttu-id="29587-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="29587-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="29587-141">Prueba con una entidad: &number;</span><span class="sxs-lookup"><span data-stu-id="29587-141">Test with an entity: &number;</span></span>|<span data-ttu-id="29587-142">Prueba con una entidad: 123</span><span class="sxs-lookup"><span data-stu-id="29587-142">Test with an entity: 123</span></span>|<span data-ttu-id="29587-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="29587-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="29587-144">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-144">\</Item></span></span>|<span data-ttu-id="29587-145">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-145">\</Item></span></span>|<span data-ttu-id="29587-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="29587-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="29587-147">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-147">\<Item></span></span>|<span data-ttu-id="29587-148">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-148">\<Item></span></span>|<span data-ttu-id="29587-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="29587-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="29587-150">prueba con un elemento secundario</span><span class="sxs-lookup"><span data-stu-id="29587-150">test with a child element</span></span>|<span data-ttu-id="29587-151">prueba con un elemento secundario</span><span class="sxs-lookup"><span data-stu-id="29587-151">test with a child element</span></span>|<span data-ttu-id="29587-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="29587-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="29587-153">\<more></span><span class="sxs-lookup"><span data-stu-id="29587-153">\<more></span></span>|<span data-ttu-id="29587-154">\<more></span><span class="sxs-lookup"><span data-stu-id="29587-154">\<more></span></span>|<span data-ttu-id="29587-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="29587-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="29587-156">stuff</span><span class="sxs-lookup"><span data-stu-id="29587-156">stuff</span></span>|<span data-ttu-id="29587-157">stuff</span><span class="sxs-lookup"><span data-stu-id="29587-157">stuff</span></span>|<span data-ttu-id="29587-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="29587-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="29587-159">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-159">\</Item></span></span>|<span data-ttu-id="29587-160">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-160">\</Item></span></span>|<span data-ttu-id="29587-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="29587-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="29587-162">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-162">\<Item></span></span>|<span data-ttu-id="29587-163">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-163">\<Item></span></span>|<span data-ttu-id="29587-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="29587-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="29587-165">prueba con una sección CDATA</span><span class="sxs-lookup"><span data-stu-id="29587-165">test with a CDATA section</span></span>|<span data-ttu-id="29587-166">prueba con una sección CDATA</span><span class="sxs-lookup"><span data-stu-id="29587-166">test with a CDATA section</span></span>|<span data-ttu-id="29587-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="29587-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="29587-168"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="29587-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="29587-169"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="29587-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="29587-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="29587-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="29587-171">def</span><span class="sxs-lookup"><span data-stu-id="29587-171">def</span></span>|<span data-ttu-id="29587-172">def</span><span class="sxs-lookup"><span data-stu-id="29587-172">def</span></span>|<span data-ttu-id="29587-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="29587-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="29587-174">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-174">\</Item></span></span>|<span data-ttu-id="29587-175">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-175">\</Item></span></span>|<span data-ttu-id="29587-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="29587-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="29587-177">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-177">\<Item></span></span>|<span data-ttu-id="29587-178">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-178">\<Item></span></span>|<span data-ttu-id="29587-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="29587-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="29587-180">Prueba con una entidad de carácter: &\#65;</span><span class="sxs-lookup"><span data-stu-id="29587-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="29587-181">Prueba con una entidad de carácter: A</span><span class="sxs-lookup"><span data-stu-id="29587-181">Test with a char entity: A</span></span>|<span data-ttu-id="29587-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="29587-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="29587-183">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-183">\</Item></span></span>|<span data-ttu-id="29587-184">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-184">\</Item></span></span>|<span data-ttu-id="29587-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="29587-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="29587-186">\<!-- Catorce caracteres en este elemento.--></span><span class="sxs-lookup"><span data-stu-id="29587-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="29587-187">\<--Catorce caracteres en este elemento.--></span><span class="sxs-lookup"><span data-stu-id="29587-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="29587-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="29587-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="29587-189">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-189">\<Item></span></span>|<span data-ttu-id="29587-190">\<Item></span><span class="sxs-lookup"><span data-stu-id="29587-190">\<Item></span></span>|<span data-ttu-id="29587-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="29587-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="29587-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="29587-192">1234567890ABCD</span></span>|<span data-ttu-id="29587-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="29587-193">1234567890ABCD</span></span>|<span data-ttu-id="29587-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="29587-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="29587-195">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-195">\</Item></span></span>|<span data-ttu-id="29587-196">\</Item></span><span class="sxs-lookup"><span data-stu-id="29587-196">\</Item></span></span>|<span data-ttu-id="29587-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="29587-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="29587-198">\</Items></span><span class="sxs-lookup"><span data-stu-id="29587-198">\</Items></span></span>|<span data-ttu-id="29587-199">\</Items></span><span class="sxs-lookup"><span data-stu-id="29587-199">\</Items></span></span>|<span data-ttu-id="29587-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="29587-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="29587-201">Debe saber qué tipo de nodo se asigna, puesto que controla qué clase de acciones son válidas y qué clase de propiedades se pueden establecer y recuperar.</span><span class="sxs-lookup"><span data-stu-id="29587-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="29587-202">La creación de nodos para espacios en blanco se controla al cargar los datos en DOM mediante la marca **PreserveWhitespace**.</span><span class="sxs-lookup"><span data-stu-id="29587-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="29587-203">Para obtener más información, vea [Control de espacios en blanco y de espacios en blanco significativos al cargar DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="29587-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="29587-204">Para agregar nuevos nodos a DOM, vea [Inserción de nodos en un documento XML](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="29587-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="29587-205">Para quitar nodos de DOM, vea [Cómo quitar nodos, contenido y valores de un documento XML](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="29587-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="29587-206">Para modificar el contenido de nodos en DOM, vea [Modificación de nodos, contenido y valores en un documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="29587-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29587-207">Vea también</span><span class="sxs-lookup"><span data-stu-id="29587-207">See also</span></span>

- [<span data-ttu-id="29587-208">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="29587-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
