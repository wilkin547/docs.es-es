---
title: Procedimiento Modificar literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 003715b04f3a5c0fb41e846beb189f117378ea58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053033"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="bb576-102">Procedimiento Modificar literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb576-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="bb576-103">Visual Basic ofrece formas cómodas modificar literales XML.</span><span class="sxs-lookup"><span data-stu-id="bb576-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="bb576-104">Puede agregar o eliminar elementos y atributos, y también puede reemplazar un elemento existente con un nuevo elemento XML.</span><span class="sxs-lookup"><span data-stu-id="bb576-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="bb576-105">Este tema proporcionan varios ejemplos de cómo modificar un literal XML existente.</span><span class="sxs-lookup"><span data-stu-id="bb576-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="bb576-106">Para modificar el valor de un literal XML</span><span class="sxs-lookup"><span data-stu-id="bb576-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="bb576-107">Para modificar el valor de un literal XML, obtenga una referencia al XML literal y establezca el `Value` propiedad en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="bb576-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="bb576-108">En el ejemplo de código siguiente se actualiza el valor de todos los \<precio > elementos de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="bb576-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="bb576-109">El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="bb576-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="bb576-110">Origen de XML:</span><span class="sxs-lookup"><span data-stu-id="bb576-110">Source XML:</span></span>

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

    <span data-ttu-id="bb576-111">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="bb576-111">Modified XML:</span></span>

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
    > <span data-ttu-id="bb576-112">El `Value` propiedad hace referencia al primer elemento XML de una colección.</span><span class="sxs-lookup"><span data-stu-id="bb576-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="bb576-113">Si hay más de un elemento que tiene el mismo nombre en una colección, al establecer el `Value` propiedad afecta a solo el primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="bb576-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="bb576-114">Para agregar un atributo a un literal XML</span><span class="sxs-lookup"><span data-stu-id="bb576-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="bb576-115">Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML.</span><span class="sxs-lookup"><span data-stu-id="bb576-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="bb576-116">A continuación, puede agregar un atributo mediante la adición de una nueva propiedad de eje de atributo XML.</span><span class="sxs-lookup"><span data-stu-id="bb576-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="bb576-117">También puede agregar un nuevo <xref:System.Xml.Linq.XAttribute> objeto al XML literal mediante el uso de la <xref:System.Xml.Linq.XContainer.Add%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bb576-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="bb576-118">El ejemplo siguiente muestra ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="bb576-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="bb576-119">El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="bb576-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="bb576-120">Origen de XML:</span><span class="sxs-lookup"><span data-stu-id="bb576-120">Source XML:</span></span>

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

    <span data-ttu-id="bb576-121">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="bb576-121">Modified XML:</span></span>

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

    <span data-ttu-id="bb576-122">Para obtener más información acerca de las propiedades de eje de atributo XML, vea [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="bb576-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="bb576-123">Para agregar un elemento a un literal XML</span><span class="sxs-lookup"><span data-stu-id="bb576-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="bb576-124">Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML.</span><span class="sxs-lookup"><span data-stu-id="bb576-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="bb576-125">A continuación, puede agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el último elemento secundario del elemento utilizando el <xref:System.Xml.Linq.XContainer.Add%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bb576-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="bb576-126">Puede agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el primer elemento secundario mediante el uso de la <xref:System.Xml.Linq.XContainer.AddFirst%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bb576-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="bb576-127">Para agregar un nuevo elemento en una ubicación específica en relación con otros subelementos, primero obtenga una referencia a un subelemento adyacente.</span><span class="sxs-lookup"><span data-stu-id="bb576-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="bb576-128">A continuación, puede agregar el nuevo <xref:System.Xml.Linq.XElement> objeto antes de que el subelemento adyacente mediante el uso de la <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bb576-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="bb576-129">También puede agregar el nuevo <xref:System.Xml.Linq.XElement> objeto después del subelemento adyacente mediante el uso de la <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bb576-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="bb576-130">El ejemplo siguiente muestra ejemplos de cada una de estas técnicas.</span><span class="sxs-lookup"><span data-stu-id="bb576-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="bb576-131">El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="bb576-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="bb576-132">Origen de XML:</span><span class="sxs-lookup"><span data-stu-id="bb576-132">Source XML:</span></span>

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

    <span data-ttu-id="bb576-133">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="bb576-133">Modified XML:</span></span>

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="bb576-134">Para quitar un elemento o atributo de un literal XML</span><span class="sxs-lookup"><span data-stu-id="bb576-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="bb576-135">Para quitar un elemento o atributo de un literal XML, obtenga una referencia al elemento o atributo y llamada la `Remove` método, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bb576-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="bb576-136">El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="bb576-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="bb576-137">Origen de XML:</span><span class="sxs-lookup"><span data-stu-id="bb576-137">Source XML:</span></span>

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

    <span data-ttu-id="bb576-138">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="bb576-138">Modified XML:</span></span>

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

    <span data-ttu-id="bb576-139">Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al XML literal y llame a la <xref:System.Xml.Linq.XElement.RemoveAll%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bb576-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="bb576-140">Para modificar un literal XML</span><span class="sxs-lookup"><span data-stu-id="bb576-140">To modify an XML literal</span></span>

1. <span data-ttu-id="bb576-141">Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento.</span><span class="sxs-lookup"><span data-stu-id="bb576-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="bb576-142">A continuación, puede crear un nuevo <xref:System.Xml.Linq.XElement> objeto que tiene un nuevo nombre y pase el nuevo <xref:System.Xml.Linq.XElement> de objeto para el <xref:System.Xml.Linq.XNode.ReplaceWith%2A> método existente <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="bb576-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="bb576-143">Si el elemento que se va a sustituir tiene los subelementos que deben conservarse, establezca el valor de la nueva <xref:System.Xml.Linq.XElement> de objeto para el <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="bb576-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="bb576-144">Esto establecerá el valor del nuevo elemento en el XML interno del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="bb576-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="bb576-145">En caso contrario, puede establecer el valor del nuevo elemento a la `Value` propiedad del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="bb576-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="bb576-146">El siguiente ejemplo de código reemplaza toda \<descripción > elementos con un \<abstracta > elemento.</span><span class="sxs-lookup"><span data-stu-id="bb576-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="bb576-147">El contenido de la \<descripción > elemento se conserva en el nuevo \<abstracta > elemento utilizando el <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad de la \<descripción > <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="bb576-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="bb576-148">El siguiente origen de XML de ejemplo muestra y se puede modificar XML de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="bb576-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="bb576-149">Origen de XML:</span><span class="sxs-lookup"><span data-stu-id="bb576-149">Source XML:</span></span>

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

    <span data-ttu-id="bb576-150">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="bb576-150">Modified XML:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bb576-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb576-151">See also</span></span>

- [<span data-ttu-id="bb576-152">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb576-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="bb576-153">XML</span><span class="sxs-lookup"><span data-stu-id="bb576-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="bb576-154">Cómo: Cargar XML desde un archivo, cadena o Stream</span><span class="sxs-lookup"><span data-stu-id="bb576-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="bb576-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="bb576-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="bb576-156">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb576-156">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
