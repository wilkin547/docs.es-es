---
title: Acceso a atributos en DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
ms.openlocfilehash: a77780621032e2ce59b9db04a179c7086588219b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291648"
---
# <a name="accessing-attributes-in-the-dom"></a>Acceso a atributos en DOM

Los atributos son propiedades del elemento, no elementos secundarios del elemento. Es importante hacer esta distinción, debido a los métodos utilizados para navegar por los nodos relacionados, principales y secundarios del DOM. Por ejemplo, los métodos **PreviousSibling** y **NextSibling** no se utilizan para navegar de un elemento a un atributo, ni entre atributos. En su lugar, un atributo es una propiedad de un elemento y pertenece a un elemento, tiene una propiedad **OwnerElement** y no una propiedad **parentNode**, y tiene métodos de navegación distintos.

Cuando el nodo actual es un elemento, utilice el método **HasAttribute** para ver si hay algún atributo asociado a dicho elemento. Una vez que se sabe que un elemento tiene atributos, existen múltiples métodos de acceso a atributos. Para recuperar un único atributo de un elemento, utilice los métodos **GetAttribute** y **GetAttributeNode** de **XmlElement**, u obtenga todos los atributos en una colección. La obtención de la colección resulta útil si es necesario recorrerla en iteración. Si desea obtener todos los atributos del elemento, utilice la propiedad **Attributes** del elemento para recuperar todos los atributos en una colección.

## <a name="retrieving-all-attributes-into-a-collection"></a>Recuperar todos los atributos en una colección

Si desea obtener todos los atributos de un nodo de elemento en una colección, llame a la propiedad **XmlElement.Attributes**. De este modo se obtiene la clase **XmlAttributeCollection** que contiene todos los atributos de un elemento. La clase **XmlAttributeCollection** se hereda de la asignación **XmlNamedNode**. Por tanto, los métodos y propiedades disponibles en la colección incluyen los disponibles en la asignación de nodo especificada, además de los métodos y propiedades específicos de la clase **XmlAttributeCollection**, como la propiedad **ItemOf** o el método **Append**. Cada elemento de la colección de atributos representa un nodo **XmlAttribute**. Para buscar el número de atributos de un elemento, obtenga la clase **XmlAttributeCollection** y utilice la propiedad **Count** para saber cuántos nodos **XmlAttribute** hay en la colección.

El siguiente ejemplo de código muestra cómo recuperar una colección de atributos y cómo utilizar el método **Count** de forma que el índice de bucle la recorra en iteración. El código muestra, a continuación, cómo recuperar un solo atributo de la colección y mostrar su valor.

```vb
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

```console
genre = novel
ISBN = 1-861001-57-5
misc = sale item
Display the attribute information.
sale item
```

La información de una colección de atributos puede recuperarse por nombre o por número de índice. El ejemplo anterior muestra cómo recuperar los datos por nombre. El ejemplo siguiente muestra cómo recuperar los datos por número de índice.

Como **XmlAttributeCollection** es una colección y se puede iterar por nombre o por índice, este ejemplo muestra la selección del primer atributo en la colección mediante un índice de base cero y mediante **baseuri.xml** como archivo de entrada.

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
        Console.WriteLine("The value of the attribute:  {0}", attr.InnerText)
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
    Console.WriteLine("The value of the attribute:  {0}", attr.InnerText);
  }
}
```

## <a name="retrieving-an-individual-attribute-node"></a>Recuperar un nodo de atributo individual

Para recuperar un solo nodo de atributo del elemento, se utiliza método <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>. Este método devuelve un objeto de tipo **XmlAttribute**. Una vez que se tiene el objeto **XmlAttribute**, todos los métodos y propiedades de la clase <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> están disponibles en ese objeto, como **OwnerElement**.

```vb
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

Se puede hacer lo mismo que en el ejemplo anterior, donde se recupera un solo nodo de atributo de la colección de atributos. El siguiente ejemplo de código muestra cómo se puede escribir una línea de código para recuperar un solo atributo por número de índice del elemento raíz del árbol de documentos XML, que también se conoce como la propiedad **DocumentElement**.

```csharp
XmlAttribute attr = doc.DocumentElement.Attributes[0];
```

## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
