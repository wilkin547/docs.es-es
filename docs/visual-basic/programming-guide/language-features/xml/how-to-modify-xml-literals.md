---
title: 'Cómo: Modificar literales XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330856"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="053ab-102">Cómo: Modificar literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="053ab-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="053ab-103">Visual Basic proporciona métodos cómodos para modificar los literales XML.</span><span class="sxs-lookup"><span data-stu-id="053ab-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="053ab-104">Puede Agregar o eliminar elementos y atributos, y también puede reemplazar un elemento existente por un nuevo elemento XML.</span><span class="sxs-lookup"><span data-stu-id="053ab-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="053ab-105">En este tema se proporcionan varios ejemplos de cómo modificar un literal XML existente.</span><span class="sxs-lookup"><span data-stu-id="053ab-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="053ab-106">Para modificar el valor de un literal XML</span><span class="sxs-lookup"><span data-stu-id="053ab-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="053ab-107">Para modificar el valor de un literal XML, obtenga una referencia al literal XML y establezca la propiedad `Value` en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="053ab-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="053ab-108">En el siguiente ejemplo de código se actualiza el valor de todos los elementos de \<Price > de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="053ab-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="053ab-109">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="053ab-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="053ab-110">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="053ab-110">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="053ab-111">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="053ab-111">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>47.20</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>48.25</Price>
      </Book>
    </Catalog>
    ```

    > [!NOTE]
    > <span data-ttu-id="053ab-112">La propiedad `Value` hace referencia al primer elemento XML de una colección.</span><span class="sxs-lookup"><span data-stu-id="053ab-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="053ab-113">Si hay más de un elemento con el mismo nombre en una colección, el establecimiento de la propiedad `Value` afecta solo al primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="053ab-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="053ab-114">Para agregar un atributo a un literal XML</span><span class="sxs-lookup"><span data-stu-id="053ab-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="053ab-115">Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML.</span><span class="sxs-lookup"><span data-stu-id="053ab-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="053ab-116">Después, puede Agregar un atributo agregando una nueva propiedad de eje de atributo XML.</span><span class="sxs-lookup"><span data-stu-id="053ab-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="053ab-117">También puede Agregar un nuevo objeto <xref:System.Xml.Linq.XAttribute> al literal XML mediante el método <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="053ab-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="053ab-118">En el ejemplo siguiente se muestran ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="053ab-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="053ab-119">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="053ab-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="053ab-120">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="053ab-120">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="053ab-121">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="053ab-121">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="053ab-122">Para obtener más información sobre las propiedades del eje de atributo XML, consulte [propiedad del eje de atributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="053ab-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="053ab-123">Para agregar un elemento a un literal XML</span><span class="sxs-lookup"><span data-stu-id="053ab-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="053ab-124">Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML.</span><span class="sxs-lookup"><span data-stu-id="053ab-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="053ab-125">Después, puede Agregar un nuevo objeto <xref:System.Xml.Linq.XElement> como el último elemento secundario del elemento mediante el método <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="053ab-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="053ab-126">Puede Agregar un nuevo objeto <xref:System.Xml.Linq.XElement> como primer subelemento mediante el método <xref:System.Xml.Linq.XContainer.AddFirst%2A>.</span><span class="sxs-lookup"><span data-stu-id="053ab-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="053ab-127">Para agregar un nuevo elemento en una ubicación específica relativa a otros subelementos, primero obtenga una referencia a un subelemento adyacente.</span><span class="sxs-lookup"><span data-stu-id="053ab-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="053ab-128">Después, puede Agregar el nuevo objeto <xref:System.Xml.Linq.XElement> antes del subelemento adyacente mediante el método <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="053ab-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="053ab-129">También puede Agregar el nuevo objeto <xref:System.Xml.Linq.XElement> después del subelemento adyacente mediante el método <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="053ab-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="053ab-130">En el ejemplo siguiente se muestran ejemplos de cada una de estas técnicas.</span><span class="sxs-lookup"><span data-stu-id="053ab-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="053ab-131">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="053ab-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="053ab-132">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="053ab-132">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="053ab-133">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="053ab-133">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331">
        <Publisher>Microsoft Press</Publisher>
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <PublishDate>2005-2-14</PublishDate>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="053ab-134">Para quitar un elemento o atributo de un literal XML</span><span class="sxs-lookup"><span data-stu-id="053ab-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="053ab-135">Para quitar un elemento o un atributo de un literal XML, obtenga una referencia al elemento o atributo y llame al método `Remove`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="053ab-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="053ab-136">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="053ab-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="053ab-137">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="053ab-137">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

    <span data-ttu-id="053ab-138">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="053ab-138">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book></Catalog>
    ```

    <span data-ttu-id="053ab-139">Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al literal XML y llame al método <xref:System.Xml.Linq.XElement.RemoveAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="053ab-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="053ab-140">Para modificar un literal XML</span><span class="sxs-lookup"><span data-stu-id="053ab-140">To modify an XML literal</span></span>

1. <span data-ttu-id="053ab-141">Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento.</span><span class="sxs-lookup"><span data-stu-id="053ab-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="053ab-142">Después, puede crear un nuevo objeto <xref:System.Xml.Linq.XElement> con un nuevo nombre y pasar el nuevo objeto <xref:System.Xml.Linq.XElement> al método <xref:System.Xml.Linq.XNode.ReplaceWith%2A> del objeto <xref:System.Xml.Linq.XElement> existente.</span><span class="sxs-lookup"><span data-stu-id="053ab-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="053ab-143">Si el elemento que se va a reemplazar tiene subelementos que se deben conservar, establezca el valor del nuevo objeto <xref:System.Xml.Linq.XElement> en la propiedad <xref:System.Xml.Linq.XContainer.Nodes%2A> del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="053ab-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="053ab-144">Esto establecerá el valor del nuevo elemento en el XML interno del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="053ab-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="053ab-145">De lo contrario, puede establecer el valor del nuevo elemento en la propiedad `Value` del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="053ab-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="053ab-146">En el ejemplo de código siguiente se reemplazan todos los elementos de la descripción \<> por un elemento \<Abstract >.</span><span class="sxs-lookup"><span data-stu-id="053ab-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="053ab-147">El contenido de la \<Descripción > elemento se conserva en el nuevo elemento \<Abstract > mediante la propiedad <xref:System.Xml.Linq.XContainer.Nodes%2A> de la descripción \<> objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="053ab-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="053ab-148">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="053ab-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="053ab-149">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="053ab-149">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
        <Description>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Description>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <Description>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Description>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="053ab-150">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="053ab-150">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <MSRP>44.95</MSRP>    <Abstract>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Abstract>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <MSRP>45.95</MSRP>    <Abstract>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Abstract>
      </Book>
    </Catalog>
    ```

## <a name="see-also"></a><span data-ttu-id="053ab-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="053ab-151">See also</span></span>

- [<span data-ttu-id="053ab-152">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="053ab-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="053ab-153">XML</span><span class="sxs-lookup"><span data-stu-id="053ab-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="053ab-154">Cargar XML desde un archivo, cadena o secuencia</span><span class="sxs-lookup"><span data-stu-id="053ab-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="053ab-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="053ab-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="053ab-156">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="053ab-156">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
