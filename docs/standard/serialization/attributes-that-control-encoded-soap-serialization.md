---
title: Atributos que controlan la serialización SOAP codificada
description: En este artículo se muestra un conjunto especial de atributos que se encuentran en el espacio de nombres System.Xml.Serialization necesario para ajustarse a la especificación SOAP.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: 69a9d1c8734a393b576cf87e7e05ef92c10120c8
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282042"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a><span data-ttu-id="d0ce0-103">Atributos que controlan la serialización SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="d0ce0-103">Attributes That Control Encoded SOAP Serialization</span></span>

<span data-ttu-id="d0ce0-104">El documento de World Wide Web Consortium (W3C) denominado [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contiene una sección opcional (sección 5) que describe cómo se pueden codificar los parámetros SOAP.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-104">The World Wide Web Consortium (W3C) document named [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contains an optional section (section 5) that describes how SOAP parameters can be encoded.</span></span> <span data-ttu-id="d0ce0-105">Para ajustarse a la sección 5 de la especificación, debe usar un conjunto especial de atributos que se encuentra en el espacio de nombres <xref:System.Xml.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-105">To conform to section 5 of the specification, you must use a special set of attributes found in the <xref:System.Xml.Serialization> namespace.</span></span> <span data-ttu-id="d0ce0-106">Aplique según corresponda esos atributos a las clases y miembros de clases y, a continuación, utilice <xref:System.Xml.Serialization.XmlSerializer> para serializar instancias de la clase o clases.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-106">Apply those attributes as appropriate to classes and members of classes, and then use the <xref:System.Xml.Serialization.XmlSerializer> to serialize instances of the class or classes.</span></span>

<span data-ttu-id="d0ce0-107">La tabla siguiente muestra los atributos, donde se pueden aplicar, y lo que hacen.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-107">The following table shows the attributes, where they can be applied, and what they do.</span></span> <span data-ttu-id="d0ce0-108">Para más información sobre el uso de estos atributos para controlar la serialización de XML, consulte [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) y [Cómo: Invalidar la serialización XML SOAP codificada](how-to-override-encoded-soap-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="d0ce0-108">For more information about using these attributes to control XML serialization, see [How to: Serialize an Object as a SOAP-Encoded XML Stream](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) and [How to: Override Encoded SOAP XML Serialization](how-to-override-encoded-soap-xml-serialization.md).</span></span>

<span data-ttu-id="d0ce0-109">Para obtener más información sobre atributos, vea [Atributos](../attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0ce0-109">For more information about attributes, see [Attributes](../attributes/index.md).</span></span>

|<span data-ttu-id="d0ce0-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="d0ce0-110">Attribute</span></span>|<span data-ttu-id="d0ce0-111">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="d0ce0-111">Applies to</span></span>|<span data-ttu-id="d0ce0-112">Especifica</span><span class="sxs-lookup"><span data-stu-id="d0ce0-112">Specifies</span></span>|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|<span data-ttu-id="d0ce0-113">Campo público, propiedad, parámetro o valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-113">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="d0ce0-114">El miembro de clase se serializará como un atributo XML.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-114">The class member will be serialized as an XML attribute.</span></span>|
|<xref:System.Xml.Serialization.SoapElementAttribute>|<span data-ttu-id="d0ce0-115">Campo público, propiedad, parámetro o valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-115">Public field, property, parameter, or return value.</span></span>|<span data-ttu-id="d0ce0-116">La clase se serializará como un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-116">The class will be serialized as an XML element.</span></span>|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|<span data-ttu-id="d0ce0-117">Campo público que es un identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-117">Public field that is an enumeration identifier.</span></span>|<span data-ttu-id="d0ce0-118">Nombre de elemento del miembro de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-118">The element name of an enumeration member.</span></span>|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|<span data-ttu-id="d0ce0-119">Propiedades públicas y campos.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-119">Public properties and fields.</span></span>|<span data-ttu-id="d0ce0-120">Se debería omitir la propiedad o campo cuando se serializa la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-120">The property or field should be ignored when the containing class is serialized.</span></span>|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|<span data-ttu-id="d0ce0-121">Declaraciones de clase derivada públicas y métodos públicos para los documentos de lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="d0ce0-121">Public-derived class declarations and public methods for Web Services Description Language (WSDL) documents.</span></span>|<span data-ttu-id="d0ce0-122">El tipo debería estar incluido al generar los esquemas (para ser reconocido cuando se serializa).</span><span class="sxs-lookup"><span data-stu-id="d0ce0-122">The type should be included when generating schemas (to be recognized when serialized).</span></span>|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|<span data-ttu-id="d0ce0-123">Declaraciones de clase públicas.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-123">Public class declarations.</span></span>|<span data-ttu-id="d0ce0-124">La clase se debería serializar como un tipo de XML.</span><span class="sxs-lookup"><span data-stu-id="d0ce0-124">The class should be serialized as an XML type.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d0ce0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0ce0-125">See also</span></span>

- [<span data-ttu-id="d0ce0-126">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="d0ce0-126">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="d0ce0-127">Cómo: Serializar un objeto como secuencia XML con codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="d0ce0-127">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [<span data-ttu-id="d0ce0-128">Cómo: Invalidar la serialización XML SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="d0ce0-128">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)
- [<span data-ttu-id="d0ce0-129">Atributos</span><span class="sxs-lookup"><span data-stu-id="d0ce0-129">Attributes</span></span>](../attributes/index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="d0ce0-130">Cómo: Serialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="d0ce0-130">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)
- [<span data-ttu-id="d0ce0-131">Cómo: Deserialización de un objeto</span><span class="sxs-lookup"><span data-stu-id="d0ce0-131">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
