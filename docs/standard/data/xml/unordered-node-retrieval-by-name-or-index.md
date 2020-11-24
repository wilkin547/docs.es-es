---
title: Recuperación de nodos desordenados por nombre o índice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
ms.openlocfilehash: e0b3b167dc43710e97a5f67fb0eb54c4742e1572
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819336"
---
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="28a95-102">Recuperación de nodos desordenados por nombre o índice</span><span class="sxs-lookup"><span data-stu-id="28a95-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="28a95-103">La clase **XmlNamedNodeMap** se describe en la especificación del W3C como NamedNodeMap y es necesaria para controlar un conjunto de nodos desordenado con la capacidad de hacer referencia a los mismos mediante su nombre o índice.</span><span class="sxs-lookup"><span data-stu-id="28a95-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="28a95-104">El único modo de acceder a una clase **XmlNamedNodeMap** es devolverla a través de un método o una propiedad.</span><span class="sxs-lookup"><span data-stu-id="28a95-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="28a95-105">Hay tres métodos o propiedades que devuelven una clase **XmlNamedNodeMap**:</span><span class="sxs-lookup"><span data-stu-id="28a95-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
- <span data-ttu-id="28a95-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="28a95-106">XmlElement.Attributes</span></span>  
  
- <span data-ttu-id="28a95-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="28a95-107">XmlDocumentType.Entities</span></span>  
  
- <span data-ttu-id="28a95-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="28a95-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="28a95-109">Por ejemplo, la propiedad **XmlDocumentType.Entities** obtiene la colección de nodos **XmlEntity** declarada en la declaración de tipos de documento.</span><span class="sxs-lookup"><span data-stu-id="28a95-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="28a95-110">Esta colección se devuelve como una clase **XmlNamedNodeMap** y se puede recorrer en iteración mediante la propiedad **Count**. También se puede mostrar información de entidad.</span><span class="sxs-lookup"><span data-stu-id="28a95-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="28a95-111">Para obtener un ejemplo de cómo recorrer en iteración una clase **XmlNamedNodeMap**, vea <xref:System.Xml.XmlDocumentType.Entities%2A>.</span><span class="sxs-lookup"><span data-stu-id="28a95-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="28a95-112">La clase **XmlAttributeCollection** se deriva de **XmlNamedNodeMap** y solo los atributos son modificables, mientras que las notaciones y entidades son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="28a95-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="28a95-113">Si utiliza **XmlNamedNodeMap** para los atributos, puede obtener nodos para dichos atributos en función de sus nombres XML.</span><span class="sxs-lookup"><span data-stu-id="28a95-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="28a95-114">De este modo se proporciona un método sencillo de manipular la colección de atributos en un nodo de elemento.</span><span class="sxs-lookup"><span data-stu-id="28a95-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="28a95-115">Esto se puede contrastar directamente con **XmlNodeList**, que también implementa la interfaz **IEnumerable**, pero con un descriptor de acceso de índice en lugar de una cadena.</span><span class="sxs-lookup"><span data-stu-id="28a95-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="28a95-116">Los métodos **RemoveNamedItem** y **SetNamedItem** solo se utilizan con respecto a **XmlAttributeCollection**.</span><span class="sxs-lookup"><span data-stu-id="28a95-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="28a95-117">Si se agrega o quita de una colección de atributos, independientemente de que se utilice la implementación de **AttributeCollection** o **XmlNamedNodeMap**, se modifica la colección de atributos del elemento.</span><span class="sxs-lookup"><span data-stu-id="28a95-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="28a95-118">En el ejemplo de código siguiente se muestra cómo se mueve un atributo y se crea un atributo nuevo.</span><span class="sxs-lookup"><span data-stu-id="28a95-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );
  
    }  
}  
```  
  
 <span data-ttu-id="28a95-119">Para ver un ejemplo de código adicional donde se muestre un atributo que se ha quitado de una clase **AttributeCollection**, vea [XmlNamedNodeMap.RemoveNamedItem (método)](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A).</span><span class="sxs-lookup"><span data-stu-id="28a95-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A).</span></span> <span data-ttu-id="28a95-120">Para más información sobre los métodos y las propiedades, vea [XmlNamedNodeMap (miembros)](xref:System.Xml.XmlNamedNodeMap).</span><span class="sxs-lookup"><span data-stu-id="28a95-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](xref:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a95-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="28a95-121">See also</span></span>

- [<span data-ttu-id="28a95-122">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="28a95-122">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
