---
title: 'Cómo: Especificar un nombre de elemento alternativo para una secuencia XML'
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
ms.openlocfilehash: 8cb6a66f9fc7a67ae99574e783fd889537b9b11a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208320"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a><span data-ttu-id="f7607-102">Cómo: Especificar un nombre de elemento alternativo para una secuencia XML</span><span class="sxs-lookup"><span data-stu-id="f7607-102">How to: Specify an Alternate Element Name for an XML Stream</span></span>
[<span data-ttu-id="f7607-103">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="f7607-103">Code Example</span></span>](#cpconoverridingserializationofclasseswithxmlattributeoverridesclassanchor1)  
  
 <span data-ttu-id="f7607-104">Usando[XmlSerializer](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx), se puede generar más de una secuencia XML con el mismo conjunto de clases.</span><span class="sxs-lookup"><span data-stu-id="f7607-104">Using the [XmlSerializer](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx), you can generate more than one XML stream with the same set of classes.</span></span> <span data-ttu-id="f7607-105">Puede que desee proceder de esta forma ya que dos servicios Web XML diferentes requieren la misma información básica, con solo ligeras diferencias.</span><span class="sxs-lookup"><span data-stu-id="f7607-105">You might want to do this because two different XML Web services require the same basic information, with only slight differences.</span></span> <span data-ttu-id="f7607-106">Por ejemplo, imagine dos servicios Web XML que procesan órdenes para los libros y así ambos requieren los números de ISBN.</span><span class="sxs-lookup"><span data-stu-id="f7607-106">For example, imagine two XML Web services that process orders for books, and thus both require ISBN numbers.</span></span> <span data-ttu-id="f7607-107">Un servicio usa la etiqueta \<ISBN> mientras el segundo usa la etiqueta \<BookID>.</span><span class="sxs-lookup"><span data-stu-id="f7607-107">One service uses the tag \<ISBN> while the second uses the tag \<BookID>.</span></span> <span data-ttu-id="f7607-108">Tiene una clase denominada `Book` que contiene un campo denominado `ISBN`.</span><span class="sxs-lookup"><span data-stu-id="f7607-108">You have a class named `Book` that contains a field named `ISBN`.</span></span> <span data-ttu-id="f7607-109">Cuando se serializa una instancia de la clase `Book`, utilizará, de forma predeterminada, el nombre de miembro (ISBN) como el nombre de elemento de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="f7607-109">When an instance of the `Book` class is serialized, it will, by default, use the member name (ISBN) as the tag element name.</span></span> <span data-ttu-id="f7607-110">Para el primer servicio Web XML, esto es como esperado.</span><span class="sxs-lookup"><span data-stu-id="f7607-110">For the first XML Web service, this is as expected.</span></span> <span data-ttu-id="f7607-111">Pero para enviar la secuencia XML al segundo servicio Web XML, debe invalidar la serialización para que el nombre de elemento de la etiqueta sea `BookID`.</span><span class="sxs-lookup"><span data-stu-id="f7607-111">But to send the XML stream to the second XML Web service, you must override the serialization so that the tag's element name is `BookID`.</span></span>  
  
### <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a><span data-ttu-id="f7607-112">Para crear una secuencia XML con un nombre de elemento alternativo</span><span class="sxs-lookup"><span data-stu-id="f7607-112">To create an XML stream with an alternate element name</span></span>  
  
1.  <span data-ttu-id="f7607-113">Cree una instancia de la clase <xref:System.Xml.Serialization.XmlElementAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f7607-113">Create an instance of the <xref:System.Xml.Serialization.XmlElementAttribute> class.</span></span>  
  
2.  <span data-ttu-id="f7607-114">Establece el <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> de <xref:System.Xml.Serialization.XmlElementAttribute> a "BookID".</span><span class="sxs-lookup"><span data-stu-id="f7607-114">Set the <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> of the <xref:System.Xml.Serialization.XmlElementAttribute> to "BookID".</span></span>  
  
3.  <span data-ttu-id="f7607-115">Cree una instancia de la clase <xref:System.Xml.Serialization.XmlAttributes>.</span><span class="sxs-lookup"><span data-stu-id="f7607-115">Create an instance of the <xref:System.Xml.Serialization.XmlAttributes> class.</span></span>  
  
4.  <span data-ttu-id="f7607-116">Agregue el objeto `XmlElementAttribute` a la colección a la que ha accedido mediante la propiedad <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> de <xref:System.Xml.Serialization.XmlAttributes> .</span><span class="sxs-lookup"><span data-stu-id="f7607-116">Add the `XmlElementAttribute` object to the collection accessed through the <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> property of <xref:System.Xml.Serialization.XmlAttributes> .</span></span>  
  
5.  <span data-ttu-id="f7607-117">Cree una instancia de la clase <xref:System.Xml.Serialization.XmlAttributeOverrides>.</span><span class="sxs-lookup"><span data-stu-id="f7607-117">Create an instance of the <xref:System.Xml.Serialization.XmlAttributeOverrides> class.</span></span>  
  
6.  <span data-ttu-id="f7607-118">Agregue `XmlAttributes` a <xref:System.Xml.Serialization.XmlAttributeOverrides>, pasando el tipo del objeto para invalidarlo y el nombre de miembro invalidado.</span><span class="sxs-lookup"><span data-stu-id="f7607-118">Add the `XmlAttributes` to the <xref:System.Xml.Serialization.XmlAttributeOverrides>, passing the type of the object to override and the name of the member being overridden.</span></span>  
  
7.  <span data-ttu-id="f7607-119">Cree una instancia de la clase `XmlSerializer` con `XmlAttributeOverrides`.</span><span class="sxs-lookup"><span data-stu-id="f7607-119">Create an instance of the `XmlSerializer` class with `XmlAttributeOverrides`.</span></span>  
  
8.  <span data-ttu-id="f7607-120">Cree una instancia de la clase `Book` y serialice o deserialícela.</span><span class="sxs-lookup"><span data-stu-id="f7607-120">Create an instance of the `Book` class, and serialize or deserialize it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7607-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7607-121">Example</span></span>  
  
```vb  
Public Class SerializeOverride()  
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
public class SerializeOverride()  
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
  
 <span data-ttu-id="f7607-122">La secuencia XML puede parecerse a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f7607-122">The XML stream might resemble the following.</span></span>  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7607-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7607-123">See also</span></span>

- <xref:System.Xml.Serialization.XmlElementAttribute>  
- <xref:System.Xml.Serialization.XmlAttributes>  
- <xref:System.Xml.Serialization.XmlAttributeOverrides>  
- [<span data-ttu-id="f7607-124">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="f7607-124">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
- [<span data-ttu-id="f7607-125">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="f7607-125">XmlSerializer</span></span>](https://msdn.microsoft.com/library/system.xml.serialization.xmlserializer.aspx)  
- [<span data-ttu-id="f7607-126">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="f7607-126">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
- [<span data-ttu-id="f7607-127">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="f7607-127">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)  
- [<span data-ttu-id="f7607-128">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="f7607-128">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
