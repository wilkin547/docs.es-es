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
# <a name="accessing-attributes-in-the-dom"></a>Acceso a atributos en DOM
Los atributos son propiedades del elemento, no elementos secundarios del elemento. Es importante hacer esta distinción, debido a los métodos utilizados para navegar por los nodos relacionados, principales y secundarios del DOM. Por ejemplo, el **PreviousSibling** y **NextSibling** métodos no se utilizan para navegar de un elemento a un atributo, ni entre atributos. En su lugar, un atributo es una propiedad de un elemento y pertenece a un elemento, tiene una **OwnerElement** propiedad y no un **parentNode** propiedad, y tiene métodos de navegación distintos.  
  
 Cuando el nodo actual es un elemento, utilice la **HasAttribute** método para ver si hay algún atributo asociado con el elemento. Una vez que se sabe que un elemento tiene atributos, existen múltiples métodos de acceso a atributos. Para recuperar un solo atributo del elemento, puede usar el **GetAttribute** y **GetAttributeNode** métodos de la **XmlElement** u obtenga todos los atributos en una colección. La obtención de la colección resulta útil si es necesario recorrerla en iteración. Si desea que todos los atributos del elemento, utilice la **atributos** propiedad del elemento para recuperar todos los atributos en una colección.  
  
## <a name="retrieving-all-attributes-into-a-collection"></a>Recuperar todos los atributos en una colección  
 Si desea que todos los atributos de un nodo de elemento en una colección, llame a la **XmlElement.Attributes** propiedad. Este modo se obtiene la **XmlAttributeCollection** que contiene todos los atributos de un elemento. El **XmlAttributeCollection** clase hereda de la **XmlNamedNode** mapa. Por lo tanto, los métodos y propiedades disponibles en la colección incluyen los disponibles en un mapa de nodo denominado además a los métodos y propiedades específicas de la **XmlAttributeCollection** de la clase, como el **ItemOf**  propiedad o el **anexado** método. Cada elemento de la colección de atributos representa un **XmlAttribute** nodo. Para buscar el número de atributos de un elemento, obtenga el **XmlAttributeCollection**y usar el **recuento** propiedad para ver cuántos **XmlAttribute** nodos están en la colección.  
  
 En el ejemplo de código siguiente se muestra cómo recuperar un atributo de colección y, mediante la **recuento** método el índice de bucle la recorra en iteración. El código muestra, a continuación, cómo recuperar un solo atributo de la colección y mostrar su valor.  
  
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
  
 Este ejemplo muestra el siguiente resultado:  
  
 **Salida**  
  
 Muestra todos los atributos en la colección.  
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 La información de una colección de atributos puede recuperarse por nombre o por número de índice. El ejemplo anterior muestra cómo recuperar los datos por nombre. El ejemplo siguiente muestra cómo recuperar los datos por número de índice.  
  
 Dado que la **XmlAttributeCollection** es una colección y se puede iterar por nombre o por índice, este ejemplo muestra la selección del primer atributo en la colección mediante un índice de base cero y mediante el siguiente archivo **baseuri.xml**como entrada.  
  
### <a name="input"></a>Entrada  
  
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
  
## <a name="retrieving-an-individual-attribute-node"></a>Recuperar un nodo de atributo individual  
 Para recuperar un solo nodo de atributo del elemento, se utiliza método <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>. Devuelve un objeto de tipo **XmlAttribute**. Una vez que tenga una **XmlAttribute**, todos los métodos y propiedades disponibles en la <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> clase están disponibles en ese objeto, como el **OwnerElement**.  
  
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
  
 Se puede hacer lo mismo que en el ejemplo anterior, donde se recupera un solo nodo de atributo de la colección de atributos. El ejemplo de código siguiente se muestra cómo se puede escribir una línea de código para recuperar un solo atributo por número de índice desde la raíz del documento XML de árbol, también se conoce como el **DocumentElement** propiedad.  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
