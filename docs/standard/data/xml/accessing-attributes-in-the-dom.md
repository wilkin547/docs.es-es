---
title: Acceso a atributos en DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="915c4-102">Acceso a atributos en DOM</span><span class="sxs-lookup"><span data-stu-id="915c4-102">Accessing Attributes in the DOM</span></span>
<span data-ttu-id="915c4-103">Los atributos son propiedades del elemento, no elementos secundarios del elemento.</span><span class="sxs-lookup"><span data-stu-id="915c4-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="915c4-104">Es importante hacer esta distinción, debido a los métodos utilizados para navegar por los nodos relacionados, principales y secundarios del DOM.</span><span class="sxs-lookup"><span data-stu-id="915c4-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="915c4-105">Por ejemplo, el **PreviousSibling** y **NextSibling** métodos no se utilizan para navegar de un elemento a un atributo, ni entre atributos.</span><span class="sxs-lookup"><span data-stu-id="915c4-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="915c4-106">En su lugar, un atributo es una propiedad de un elemento y pertenece a un elemento, tiene una **OwnerElement** propiedad y no un **parentNode** propiedad, y tiene métodos de navegación distintos.</span><span class="sxs-lookup"><span data-stu-id="915c4-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>  
  
 <span data-ttu-id="915c4-107">Cuando el nodo actual es un elemento, utilice la **HasAttribute** método para ver si hay algún atributo asociado con el elemento.</span><span class="sxs-lookup"><span data-stu-id="915c4-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="915c4-108">Una vez que se sabe que un elemento tiene atributos, existen múltiples métodos de acceso a atributos.</span><span class="sxs-lookup"><span data-stu-id="915c4-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="915c4-109">Para recuperar un solo atributo del elemento, puede usar el **GetAttribute** y **GetAttributeNode** métodos de la **XmlElement** u obtenga todos los atributos en una colección.</span><span class="sxs-lookup"><span data-stu-id="915c4-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="915c4-110">La obtención de la colección resulta útil si es necesario recorrerla en iteración.</span><span class="sxs-lookup"><span data-stu-id="915c4-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="915c4-111">Si desea que todos los atributos del elemento, utilice la **atributos** propiedad del elemento para recuperar todos los atributos en una colección.</span><span class="sxs-lookup"><span data-stu-id="915c4-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>  
  
## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="915c4-112">Recuperar todos los atributos en una colección</span><span class="sxs-lookup"><span data-stu-id="915c4-112">Retrieving All Attributes into a Collection</span></span>  
 <span data-ttu-id="915c4-113">Si desea que todos los atributos de un nodo de elemento en una colección, llame a la **XmlElement.Attributes** propiedad.</span><span class="sxs-lookup"><span data-stu-id="915c4-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="915c4-114">Este modo se obtiene la **XmlAttributeCollection** que contiene todos los atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="915c4-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="915c4-115">El **XmlAttributeCollection** clase hereda de la **XmlNamedNode** mapa.</span><span class="sxs-lookup"><span data-stu-id="915c4-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="915c4-116">Por lo tanto, los métodos y propiedades disponibles en la colección incluyen los disponibles en un mapa de nodo denominado además a los métodos y propiedades específicas de la **XmlAttributeCollection** de la clase, como el **ItemOf**  propiedad o el **anexado** método.</span><span class="sxs-lookup"><span data-stu-id="915c4-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="915c4-117">Cada elemento de la colección de atributos representa un **XmlAttribute** nodo.</span><span class="sxs-lookup"><span data-stu-id="915c4-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="915c4-118">Para buscar el número de atributos de un elemento, obtenga el **XmlAttributeCollection**y usar el **recuento** propiedad para ver cuántos **XmlAttribute** nodos están en la colección.</span><span class="sxs-lookup"><span data-stu-id="915c4-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>  
  
 <span data-ttu-id="915c4-119">En el ejemplo de código siguiente se muestra cómo recuperar un atributo de colección y, mediante la **recuento** método el índice de bucle la recorra en iteración.</span><span class="sxs-lookup"><span data-stu-id="915c4-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="915c4-120">El código muestra, a continuación, cómo recuperar un solo atributo de la colección y mostrar su valor.</span><span class="sxs-lookup"><span data-stu-id="915c4-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.   
        Dim myElement As XmlElement = doc.DocumentElement  
  
        ' Create an attribute collection from the element.  
        Dim attrColl As XmlAttributeCollection = myElement.Attributes  
  
        ' Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...")  
        Dim i As Integer  
        For i = 0 To attrColl.Count - 1  
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)  
            Console.Write("{0}", attrColl.ItemOf(i).Value)  
            Console.WriteLine()  
        Next  
  
        ' Retrieve a single attribute from the collection; specifically, the  
        ' attribute with the name "misc".  
        Dim attr As XmlAttribute = attrColl("misc")  
  
        ' Retrieve the value from that attribute.  
        Dim miscValue As String = attr.InnerXml  
  
        Console.WriteLine("Display the attribute information.")  
        Console.WriteLine(miscValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  
    public static void Main()  
    {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +  
                      "<title>The Handmaid's Tale</title>" +  
                      "<price>14.95</price>" +  
                      "</book>");  
  
        // Move to an element.  
        XmlElement myElement = doc.DocumentElement;  
  
        // Create an attribute collection from the element.  
        XmlAttributeCollection attrColl = myElement.Attributes;  
  
        // Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...");  
        for (int i = 0; i < attrColl.Count; i++)  
        {  
            Console.Write("{0} = ", attrColl[i].Name);  
            Console.Write("{0}", attrColl[i].Value);  
            Console.WriteLine();  
        }  
  
        // Retrieve a single attribute from the collection; specifically, the  
        // attribute with the name "misc".  
        XmlAttribute attr = attrColl["misc"];  
  
        // Retrieve the value from that attribute.  
        String miscValue = attr.InnerXml;  
  
        Console.WriteLine("Display the attribute information.");  
        Console.WriteLine(miscValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="915c4-121">Este ejemplo muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="915c4-121">This example displays the following output:</span></span>  
  
 <span data-ttu-id="915c4-122">**Salida**</span><span class="sxs-lookup"><span data-stu-id="915c4-122">**Output**</span></span>  
  
 <span data-ttu-id="915c4-123">Muestra todos los atributos en la colección.</span><span class="sxs-lookup"><span data-stu-id="915c4-123">Display all the attributes in the collection.</span></span>  
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 <span data-ttu-id="915c4-124">La información de una colección de atributos puede recuperarse por nombre o por número de índice.</span><span class="sxs-lookup"><span data-stu-id="915c4-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="915c4-125">El ejemplo anterior muestra cómo recuperar los datos por nombre.</span><span class="sxs-lookup"><span data-stu-id="915c4-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="915c4-126">El ejemplo siguiente muestra cómo recuperar los datos por número de índice.</span><span class="sxs-lookup"><span data-stu-id="915c4-126">The next example shows how to retrieve data by index number.</span></span>  
  
 <span data-ttu-id="915c4-127">Dado que la **XmlAttributeCollection** es una colección y se puede iterar por nombre o por índice, este ejemplo muestra la selección del primer atributo en la colección mediante un índice de base cero y mediante el siguiente archivo **baseuri.xml**como entrada.</span><span class="sxs-lookup"><span data-stu-id="915c4-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>  
  
### <a name="input"></a><span data-ttu-id="915c4-128">Entrada</span><span class="sxs-lookup"><span data-stu-id="915c4-128">Input</span></span>  
  
```xml  
<!-- XML fragment -->  
<book genre="novel">  
  <title>Pride And Prejudice</title>  
</book>  
```  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.Load("http://localhost/baseuri.xml")  
  
        ' Display information on the attribute node. The value  
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.  
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)  
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)  
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)  
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
    End Sub 'Main   
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    // Create the XmlDocument.  
    XmlDocument doc = new XmlDocument();  
  
    doc.Load("http://localhost/baseuri.xml");  
  
    // Display information on the attribute node. The value  
    // returned for BaseURI is 'http://localhost/baseuri.xml'.  
    XmlAttribute attr = doc.DocumentElement.Attributes[0];  
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);  
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);  
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="915c4-129">Recuperar un nodo de atributo individual</span><span class="sxs-lookup"><span data-stu-id="915c4-129">Retrieving an Individual Attribute Node</span></span>  
 <span data-ttu-id="915c4-130">Para recuperar un solo nodo de atributo del elemento, se utiliza método <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="915c4-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="915c4-131">Devuelve un objeto de tipo **XmlAttribute**.</span><span class="sxs-lookup"><span data-stu-id="915c4-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="915c4-132">Una vez que tenga una **XmlAttribute**, todos los métodos y propiedades disponibles en la <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> clase están disponibles en ese objeto, como el **OwnerElement**.</span><span class="sxs-lookup"><span data-stu-id="915c4-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.  
        Dim root As XmlElement  
        root = doc.DocumentElement  
  
        ' Get an attribute.  
        Dim attr As XmlAttribute  
        attr = root.GetAttributeNode("ISBN")  
  
        ' Display the value of the attribute.  
        Dim attrValue As String  
        attrValue = attr.InnerXml  
        Console.WriteLine(attrValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
 public class Sample  
 {  
      public static void Main()  
      {  
    XmlDocument doc = new XmlDocument();  
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +  
                   "<title>The Handmaid's Tale</title>" +  
                   "<price>14.95</price>" +  
                   "</book>");   
  
    // Move to an element.  
     XmlElement root = doc.DocumentElement;  
  
    // Get an attribute.  
     XmlAttribute attr = root.GetAttributeNode("ISBN");  
  
    // Display the value of the attribute.  
     String attrValue = attr.InnerXml;  
     Console.WriteLine(attrValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="915c4-133">Se puede hacer lo mismo que en el ejemplo anterior, donde se recupera un solo nodo de atributo de la colección de atributos.</span><span class="sxs-lookup"><span data-stu-id="915c4-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="915c4-134">El ejemplo de código siguiente se muestra cómo se puede escribir una línea de código para recuperar un solo atributo por número de índice desde la raíz del documento XML de árbol, también se conoce como el **DocumentElement** propiedad.</span><span class="sxs-lookup"><span data-stu-id="915c4-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a><span data-ttu-id="915c4-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="915c4-135">See Also</span></span>  
 [<span data-ttu-id="915c4-136">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="915c4-136">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
