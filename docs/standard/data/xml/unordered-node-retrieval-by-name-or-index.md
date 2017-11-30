---
title: "Recuperación de nodos desordenados por nombre o índice"
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
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8bea8f373dced08fd7a2a828255a593533df9d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="7edf9-102">Recuperación de nodos desordenados por nombre o índice</span><span class="sxs-lookup"><span data-stu-id="7edf9-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="7edf9-103">El **XmlNamedNodeMap** se describe en la especificación de World Wide Web Consortium (W3C) como NamedNodeMap y es necesario para controlar un conjunto de nodos desordenado con la capacidad de los nodos de referencia por su nombre o índice.</span><span class="sxs-lookup"><span data-stu-id="7edf9-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="7edf9-104">La única manera de tiene acceso a un **XmlNamedNodeMap** es cuando un **XmlNamedNodeMap** se devuelve a través de un método o propiedad.</span><span class="sxs-lookup"><span data-stu-id="7edf9-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="7edf9-105">Hay tres métodos o propiedades que devuelven un **XmlNamedNodeMap**:</span><span class="sxs-lookup"><span data-stu-id="7edf9-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
-   <span data-ttu-id="7edf9-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="7edf9-106">XmlElement.Attributes</span></span>  
  
-   <span data-ttu-id="7edf9-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="7edf9-107">XmlDocumentType.Entities</span></span>  
  
-   <span data-ttu-id="7edf9-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="7edf9-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="7edf9-109">Por ejemplo, el **XmlDocumentType.Entities** propiedad obtiene la colección de **XmlEntity** nodos declaran en la declaración de tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="7edf9-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="7edf9-110">Esta colección se devuelve como un **XmlNamedNodeMap**, y puede recorrer en iteración la colección mediante el uso de la **recuento** propiedad y mostrar información de la entidad.</span><span class="sxs-lookup"><span data-stu-id="7edf9-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="7edf9-111">Para obtener un ejemplo de cómo recorrer un **XmlNamedNodeMap**, consulte <xref:System.Xml.XmlDocumentType.Entities%2A>.</span><span class="sxs-lookup"><span data-stu-id="7edf9-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="7edf9-112">El **XmlAttributeCollection** se deriva de **XmlNamedNodeMap** y sólo los atributos son modificables, mientras que las notaciones y entidades son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="7edf9-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="7edf9-113">Mediante el **XmlNamedNodeMap** para los atributos, puede obtener nodos para dichos atributos en función de sus nombres XML.</span><span class="sxs-lookup"><span data-stu-id="7edf9-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="7edf9-114">De este modo se proporciona un método sencillo de manipular la colección de atributos en un nodo de elemento.</span><span class="sxs-lookup"><span data-stu-id="7edf9-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="7edf9-115">Esto se puede contrastar directamente con **XmlNodeList**, que también implementa la **IEnumerable** interfaz, pero con un descriptor de acceso de índice en lugar de una cadena.</span><span class="sxs-lookup"><span data-stu-id="7edf9-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="7edf9-116">El **RemoveNamedItem** y **SetNamedItem** métodos solo se utilicen en una **XmlAttributeCollection**.</span><span class="sxs-lookup"><span data-stu-id="7edf9-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="7edf9-117">Agregar o quitar de una colección de atributos, independientemente de si usa la **AttributeCollection** o **XmlNamedNodeMap** implementación, modifica la colección de atributos en el elemento.</span><span class="sxs-lookup"><span data-stu-id="7edf9-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="7edf9-118">En el ejemplo de código siguiente se muestra cómo se mueve un atributo y se crea un atributo nuevo.</span><span class="sxs-lookup"><span data-stu-id="7edf9-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
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
  
 <span data-ttu-id="7edf9-119">Para ver un ejemplo de código adicional donde se muestre un atributo que se va a quitar de un **AttributeCollection**, consulte [XmlNamedNodeMap.RemoveNamedItem (método)](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span><span class="sxs-lookup"><span data-stu-id="7edf9-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span></span> <span data-ttu-id="7edf9-120">Para obtener más información sobre los métodos y propiedades, vea [XmlNamedNodeMap Members](AllMembers.T:System.Xml.XmlNamedNodeMap).</span><span class="sxs-lookup"><span data-stu-id="7edf9-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](AllMembers.T:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edf9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="7edf9-121">See Also</span></span>  
 [<span data-ttu-id="7edf9-122">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="7edf9-122">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
