---
title: Procedimiento para especificar un nombre de elemento alternativo para una secuencia XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: 2dc1110b858f639624e05382a67ddccf3ea1b047
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588461"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a><span data-ttu-id="b3461-102">Procedimiento para especificar un nombre de elemento alternativo para una secuencia XML</span><span class="sxs-lookup"><span data-stu-id="b3461-102">How to: Specify an Alternate Element Name for an XML Stream</span></span>
  
<span data-ttu-id="b3461-103">Utilizando<xref:System.Xml.Serialization.XmlSerializer>, se puede generar más de una secuencia XML con el mismo conjunto de clases.</span><span class="sxs-lookup"><span data-stu-id="b3461-103">Using the <xref:System.Xml.Serialization.XmlSerializer>, you can generate more than one XML stream with the same set of classes.</span></span> <span data-ttu-id="b3461-104">Puede que desee proceder de esta forma ya que dos servicios Web XML diferentes requieren la misma información básica, con solo ligeras diferencias.</span><span class="sxs-lookup"><span data-stu-id="b3461-104">You might want to do this because two different XML Web services require the same basic information, with only slight differences.</span></span> <span data-ttu-id="b3461-105">Por ejemplo, imagine dos servicios Web XML que procesan órdenes para los libros y así ambos requieren los números de ISBN.</span><span class="sxs-lookup"><span data-stu-id="b3461-105">For example, imagine two XML Web services that process orders for books, and thus both require ISBN numbers.</span></span> <span data-ttu-id="b3461-106">Un servicio usa la etiqueta \<ISBN> mientras el segundo usa la etiqueta \<BookID>.</span><span class="sxs-lookup"><span data-stu-id="b3461-106">One service uses the tag \<ISBN> while the second uses the tag \<BookID>.</span></span> <span data-ttu-id="b3461-107">Tiene una clase denominada `Book` que contiene un campo denominado `ISBN`.</span><span class="sxs-lookup"><span data-stu-id="b3461-107">You have a class named `Book` that contains a field named `ISBN`.</span></span> <span data-ttu-id="b3461-108">Cuando se serializa una instancia de la clase `Book`, utilizará, de forma predeterminada, el nombre de miembro (ISBN) como el nombre de elemento de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b3461-108">When an instance of the `Book` class is serialized, it will, by default, use the member name (ISBN) as the tag element name.</span></span> <span data-ttu-id="b3461-109">Para el primer servicio Web XML, esto es como esperado.</span><span class="sxs-lookup"><span data-stu-id="b3461-109">For the first XML Web service, this is as expected.</span></span> <span data-ttu-id="b3461-110">Pero para enviar la secuencia XML al segundo servicio Web XML, debe invalidar la serialización para que el nombre de elemento de la etiqueta sea `BookID`.</span><span class="sxs-lookup"><span data-stu-id="b3461-110">But to send the XML stream to the second XML Web service, you must override the serialization so that the tag's element name is `BookID`.</span></span>  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a><span data-ttu-id="b3461-111">Para crear una secuencia XML con un nombre de elemento alternativo</span><span class="sxs-lookup"><span data-stu-id="b3461-111">To create an XML stream with an alternate element name</span></span>  
  
1. <span data-ttu-id="b3461-112">Cree una instancia de la clase <xref:System.Xml.Serialization.XmlElementAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b3461-112">Create an instance of the <xref:System.Xml.Serialization.XmlElementAttribute> class.</span></span>  
  
2. <span data-ttu-id="b3461-113">Establece el <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> de <xref:System.Xml.Serialization.XmlElementAttribute> a "BookID".</span><span class="sxs-lookup"><span data-stu-id="b3461-113">Set the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> of the <xref:System.Xml.Serialization.XmlElementAttribute> to "BookID".</span></span>  
  
3. <span data-ttu-id="b3461-114">Cree una instancia de la clase <xref:System.Xml.Serialization.XmlAttributes>.</span><span class="sxs-lookup"><span data-stu-id="b3461-114">Create an instance of the <xref:System.Xml.Serialization.XmlAttributes> class.</span></span>  
  
4. <span data-ttu-id="b3461-115">Agregue el objeto `XmlElementAttribute` a la colección a la que ha accedido mediante la propiedad <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> de <xref:System.Xml.Serialization.XmlAttributes> .</span><span class="sxs-lookup"><span data-stu-id="b3461-115">Add the `XmlElementAttribute` object to the collection accessed through the <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> property of <xref:System.Xml.Serialization.XmlAttributes> .</span></span>  
  
5. <span data-ttu-id="b3461-116">Cree una instancia de la clase <xref:System.Xml.Serialization.XmlAttributeOverrides>.</span><span class="sxs-lookup"><span data-stu-id="b3461-116">Create an instance of the <xref:System.Xml.Serialization.XmlAttributeOverrides> class.</span></span>  
  
6. <span data-ttu-id="b3461-117">Agregue `XmlAttributes` a <xref:System.Xml.Serialization.XmlAttributeOverrides>, pasando el tipo del objeto para invalidarlo y el nombre de miembro invalidado.</span><span class="sxs-lookup"><span data-stu-id="b3461-117">Add the `XmlAttributes` to the <xref:System.Xml.Serialization.XmlAttributeOverrides>, passing the type of the object to override and the name of the member being overridden.</span></span>  
  
7. <span data-ttu-id="b3461-118">Cree una instancia de la clase `XmlSerializer` con `XmlAttributeOverrides`.</span><span class="sxs-lookup"><span data-stu-id="b3461-118">Create an instance of the `XmlSerializer` class with `XmlAttributeOverrides`.</span></span>  
  
8. <span data-ttu-id="b3461-119">Cree una instancia de la clase `Book` y serialice o deserialícela.</span><span class="sxs-lookup"><span data-stu-id="b3461-119">Create an instance of the `Book` class, and serialize or deserialize it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3461-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3461-120">Example</span></span>  
  
```vb  
Public Function SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public void SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 <span data-ttu-id="b3461-121">La secuencia XML puede parecerse a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3461-121">The XML stream might resemble the following.</span></span>  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3461-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3461-122">See also</span></span>

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [<span data-ttu-id="b3461-123">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="b3461-123">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="b3461-124">Cómo: para serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="b3461-124">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [<span data-ttu-id="b3461-125">Cómo: para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="b3461-125">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
