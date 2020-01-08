---
title: Cómo calificar nombres de atributos XML y elementos XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: 383dc7687e67e183b86598857067801c950b0312
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545093"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="4cdf3-102">Cómo calificar nombres de atributos XML y elementos XML</span><span class="sxs-lookup"><span data-stu-id="4cdf3-102">How to qualify XML element and XML attribute names</span></span>

<span data-ttu-id="4cdf3-103">Los espacios de nombres XML contenidos en instancias de la clase <xref:System.Xml.Serialization.XmlSerializerNamespaces> deben ajustarse a la especificación de World Wide Web Consortium (W3C) denominada [espacios de nombres en XML](https://www.w3.org/TR/REC-xml-names/).</span><span class="sxs-lookup"><span data-stu-id="4cdf3-103">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="4cdf3-104">Los espacios de nombres XML proporcionan una método para calificar los nombres de elementos y atributos XML en documentos XML.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-104">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="4cdf3-105">Un nombre calificado se compone de un prefijo y un nombre local, separados por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-105">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="4cdf3-106">El prefijo funciona únicamente como marcador de posición y está asignado a un identificador URI que especifica un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-106">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="4cdf3-107">La combinación del espacio de nombres del URI, universalmente administrado, y el nombre local genera un nombre del que se garantiza que es universalmente único.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-107">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="4cdf3-108">Creando una instancia de `XmlSerializerNamespaces` y agregando los pares de espacio de nombres al objeto, puede especificar los prefijos utilizados en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-108">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="4cdf3-109">Para crear nombres calificados en un documento XML</span><span class="sxs-lookup"><span data-stu-id="4cdf3-109">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="4cdf3-110">Cree una instancia de la clase `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-110">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="4cdf3-111">Agregue todos los prefijos y pares de espacio de nombres a `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-111">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="4cdf3-112">Aplique el atributo apropiado `System.Xml.Serialization` a cada método o clase que <xref:System.Xml.Serialization.XmlSerializer> vaya a serializar en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-112">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

    <span data-ttu-id="4cdf3-113">Los atributos disponibles son: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, y <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-113">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="4cdf3-114">Establezca la propiedad `Namespace` de cada atributo en uno de los valores de espacio de nombres del `XmlSerializerNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-114">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="4cdf3-115">Pase `XmlSerializerNamespaces` al método `Serialize` de `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-115">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="4cdf3-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4cdf3-116">Example</span></span>

<span data-ttu-id="4cdf3-117">En el siguiente ejemplo, se crea un `XmlSerializerNamespaces` al que se agregan dos prefijos y pares de espacio de nombres al objeto.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-117">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="4cdf3-118">El código crea `XmlSerializer` que se utiliza para serializar una instancia de la clase `Books`.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-118">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="4cdf3-119">El código llama al método `Serialize` con `XmlSerializerNamespaces`, permitiéndole al XML contener los espacios de nombres prefijados.</span><span class="sxs-lookup"><span data-stu-id="4cdf3-119">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Module Program

    Public Sub Main()
        SerializeObject("XmlNamespaces.xml")
    End Sub

    Public Sub SerializeObject(filename As String)
        Dim mySerializer As New XmlSerializer(GetType(Books))
        ' Writing a file requires a TextWriter.
        Dim myWriter As New StreamWriter(filename)

        ' Creates an XmlSerializerNamespaces and adds two
        ' prefix-namespace pairs.
        Dim myNamespaces As New XmlSerializerNamespaces()
        myNamespaces.Add("books", "http://www.cpandl.com")
        myNamespaces.Add("money", "http://www.cohowinery.com")

        ' Creates a Book.
        Dim myBook As New Book()
        myBook.TITLE = "A Book Title"
        Dim myPrice As New Price()
        myPrice.price = CDec(9.95)
        myPrice.currency = "US Dollar"
        myBook.PRICE = myPrice
        Dim myBooks As New Books()
        myBooks.Book = myBook
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)
        myWriter.Close()
    End Sub
End Module

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class

<XmlType([Namespace] := "http://www.cpandl.com")> _
Public Class Book
    <XmlElement([Namespace] := "http://www.cpandl.com")> _
    Public TITLE As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public PRICE As Price
End Class

Public Class Price
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _
    Public currency As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Program
{
    public static void Main()
    {
        SerializeObject("XmlNamespaces.xml");
    }
    
    public static void SerializeObject(string filename)
    {
        var mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        var myNamespaces = new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        var myBook = new Book();
        myBook.TITLE = "A Book Title";
        var myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        var myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter, myBooks, myNamespaces);
        myWriter.Close();
    }
}

public class Books
{
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public Book Book;
}

[XmlType(Namespace ="http://www.cpandl.com")]
public class Book
{
    [XmlElement(Namespace = "http://www.cpandl.com")]
    public string TITLE;
    [XmlElement(Namespace ="http://www.cohowinery.com")]
    public Price PRICE;
}

public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}
```

## <a name="see-also"></a><span data-ttu-id="4cdf3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cdf3-120">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="4cdf3-121">Herramienta de definición de esquema XML y serialización XML</span><span class="sxs-lookup"><span data-stu-id="4cdf3-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="4cdf3-122">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="4cdf3-122">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="4cdf3-123">XmlSerializer (clase)</span><span class="sxs-lookup"><span data-stu-id="4cdf3-123">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)
- [<span data-ttu-id="4cdf3-124">Atributos que controlan la serialización XML</span><span class="sxs-lookup"><span data-stu-id="4cdf3-124">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- [<span data-ttu-id="4cdf3-125">Cómo: Especificar un nombre de elemento alternativo para una secuencia XML</span><span class="sxs-lookup"><span data-stu-id="4cdf3-125">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [<span data-ttu-id="4cdf3-126">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="4cdf3-126">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="4cdf3-127">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="4cdf3-127">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
