---
description: 'Más información acerca de cómo: modificar literales XML (Visual Basic)'
title: Procedimiento para modificar literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 23b900c3da5864ac7a91e6c7a43f44a0d4ab1a21
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483617"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="89f92-103">Cómo: Modificar literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89f92-103">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="89f92-104">Visual Basic proporciona métodos cómodos para modificar los literales XML.</span><span class="sxs-lookup"><span data-stu-id="89f92-104">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="89f92-105">Puede Agregar o eliminar elementos y atributos, y también puede reemplazar un elemento existente por un nuevo elemento XML.</span><span class="sxs-lookup"><span data-stu-id="89f92-105">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="89f92-106">En este tema se proporcionan varios ejemplos de cómo modificar un literal XML existente.</span><span class="sxs-lookup"><span data-stu-id="89f92-106">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="89f92-107">Para modificar el valor de un literal XML</span><span class="sxs-lookup"><span data-stu-id="89f92-107">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="89f92-108">Para modificar el valor de un literal XML, obtenga una referencia al literal XML y establezca la `Value` propiedad en el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="89f92-108">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="89f92-109">En el siguiente ejemplo de código se actualiza el valor de todos los \<Price> elementos de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="89f92-109">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="89f92-110">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="89f92-110">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="89f92-111">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="89f92-111">Source XML:</span></span>

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

    <span data-ttu-id="89f92-112">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="89f92-112">Modified XML:</span></span>

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
    > <span data-ttu-id="89f92-113">La `Value` propiedad hace referencia al primer elemento XML de una colección.</span><span class="sxs-lookup"><span data-stu-id="89f92-113">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="89f92-114">Si hay más de un elemento con el mismo nombre en una colección, el establecimiento de la `Value` propiedad afecta solo al primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="89f92-114">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="89f92-115">Para agregar un atributo a un literal XML</span><span class="sxs-lookup"><span data-stu-id="89f92-115">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="89f92-116">Para agregar un atributo a un literal XML, primero obtenga una referencia al literal XML.</span><span class="sxs-lookup"><span data-stu-id="89f92-116">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="89f92-117">Después, puede Agregar un atributo agregando una nueva propiedad de eje de atributo XML.</span><span class="sxs-lookup"><span data-stu-id="89f92-117">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="89f92-118">También puede Agregar un nuevo <xref:System.Xml.Linq.XAttribute> objeto al literal XML mediante el <xref:System.Xml.Linq.XContainer.Add%2A> método.</span><span class="sxs-lookup"><span data-stu-id="89f92-118">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="89f92-119">En el ejemplo siguiente se muestran ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="89f92-119">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="89f92-120">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="89f92-120">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="89f92-121">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="89f92-121">Source XML:</span></span>

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

    <span data-ttu-id="89f92-122">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="89f92-122">Modified XML:</span></span>

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

    <span data-ttu-id="89f92-123">Para obtener más información sobre las propiedades del eje de atributo XML, consulte [propiedad del eje de atributo XML](../../../language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="89f92-123">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="89f92-124">Para agregar un elemento a un literal XML</span><span class="sxs-lookup"><span data-stu-id="89f92-124">To add an element to an XML literal</span></span>

1. <span data-ttu-id="89f92-125">Para agregar un elemento a un literal XML, primero obtenga una referencia al literal XML.</span><span class="sxs-lookup"><span data-stu-id="89f92-125">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="89f92-126">Después, puede Agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como el último elemento secundario del elemento mediante el <xref:System.Xml.Linq.XContainer.Add%2A> método.</span><span class="sxs-lookup"><span data-stu-id="89f92-126">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="89f92-127">Puede Agregar un nuevo <xref:System.Xml.Linq.XElement> objeto como primer subelemento mediante el <xref:System.Xml.Linq.XContainer.AddFirst%2A> método.</span><span class="sxs-lookup"><span data-stu-id="89f92-127">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="89f92-128">Para agregar un nuevo elemento en una ubicación específica relativa a otros subelementos, primero obtenga una referencia a un subelemento adyacente.</span><span class="sxs-lookup"><span data-stu-id="89f92-128">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="89f92-129">Después, puede Agregar el nuevo <xref:System.Xml.Linq.XElement> objeto delante del subelemento adyacente mediante el <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> método.</span><span class="sxs-lookup"><span data-stu-id="89f92-129">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="89f92-130">También puede Agregar el nuevo <xref:System.Xml.Linq.XElement> objeto después del subelemento adyacente mediante el <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> método.</span><span class="sxs-lookup"><span data-stu-id="89f92-130">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="89f92-131">En el ejemplo siguiente se muestran ejemplos de cada una de estas técnicas.</span><span class="sxs-lookup"><span data-stu-id="89f92-131">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="89f92-132">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="89f92-132">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="89f92-133">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="89f92-133">Source XML:</span></span>

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

    <span data-ttu-id="89f92-134">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="89f92-134">Modified XML:</span></span>

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="89f92-135">Para quitar un elemento o atributo de un literal XML</span><span class="sxs-lookup"><span data-stu-id="89f92-135">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="89f92-136">Para quitar un elemento o un atributo de un literal XML, obtenga una referencia al elemento o atributo y llame al `Remove` método, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="89f92-136">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="89f92-137">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="89f92-137">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="89f92-138">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="89f92-138">Source XML:</span></span>

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

    <span data-ttu-id="89f92-139">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="89f92-139">Modified XML:</span></span>

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

    <span data-ttu-id="89f92-140">Para quitar todos los elementos o atributos de un literal XML, obtenga una referencia al literal XML y llame al <xref:System.Xml.Linq.XElement.RemoveAll%2A> método.</span><span class="sxs-lookup"><span data-stu-id="89f92-140">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="89f92-141">Para modificar un literal XML</span><span class="sxs-lookup"><span data-stu-id="89f92-141">To modify an XML literal</span></span>

1. <span data-ttu-id="89f92-142">Para cambiar el nombre de un elemento XML, primero obtenga una referencia al elemento.</span><span class="sxs-lookup"><span data-stu-id="89f92-142">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="89f92-143">Después, puede crear un nuevo <xref:System.Xml.Linq.XElement> objeto que tenga un nuevo nombre y pasar el nuevo <xref:System.Xml.Linq.XElement> objeto al <xref:System.Xml.Linq.XNode.ReplaceWith%2A> método del <xref:System.Xml.Linq.XElement> objeto existente.</span><span class="sxs-lookup"><span data-stu-id="89f92-143">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="89f92-144">Si el elemento que va a reemplazar tiene subelementos que deben conservarse, establezca el valor del nuevo <xref:System.Xml.Linq.XElement> objeto en la <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="89f92-144">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="89f92-145">Esto establecerá el valor del nuevo elemento en el XML interno del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="89f92-145">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="89f92-146">De lo contrario, puede establecer el valor del nuevo elemento en la `Value` propiedad del elemento existente.</span><span class="sxs-lookup"><span data-stu-id="89f92-146">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="89f92-147">En el siguiente ejemplo de código se reemplazan todos los \<Description> elementos por un \<Abstract> elemento.</span><span class="sxs-lookup"><span data-stu-id="89f92-147">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="89f92-148">El contenido del \<Description> elemento se conserva en el nuevo \<Abstract> elemento mediante la <xref:System.Xml.Linq.XContainer.Nodes%2A> propiedad del \<Description> <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="89f92-148">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="89f92-149">A continuación se muestra el XML de origen de ejemplo y el XML modificado de este ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="89f92-149">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="89f92-150">XML de origen:</span><span class="sxs-lookup"><span data-stu-id="89f92-150">Source XML:</span></span>

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

    <span data-ttu-id="89f92-151">XML modificado:</span><span class="sxs-lookup"><span data-stu-id="89f92-151">Modified XML:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="89f92-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89f92-152">See also</span></span>

- [<span data-ttu-id="89f92-153">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89f92-153">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="89f92-154">XML</span><span class="sxs-lookup"><span data-stu-id="89f92-154">XML</span></span>](index.md)
- [<span data-ttu-id="89f92-155">Procedimiento para cargar XML desde un archivo, cadena o secuencia</span><span class="sxs-lookup"><span data-stu-id="89f92-155">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="89f92-156">LINQ</span><span class="sxs-lookup"><span data-stu-id="89f92-156">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="89f92-157">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89f92-157">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
