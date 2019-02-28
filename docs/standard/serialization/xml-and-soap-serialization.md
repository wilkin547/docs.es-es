---
title: Serialización de SOAP y XML
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: d9dc68d8e7eced031af404aaec20784573c9930a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965623"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="0a6c3-102">Serialización de SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-102">XML and SOAP Serialization</span></span>

<span data-ttu-id="0a6c3-103">La serialización XML convierte (serializa) las propiedades y campos públicos de un objeto o los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="0a6c3-103">XML serialization converts (serializes) the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="0a6c3-104">La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie (en este caso, a XML) para almacenaje y transporte.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="0a6c3-105">Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="0a6c3-106">Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="0a6c3-107">A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="0a6c3-108">La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="0a6c3-109">SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="0a6c3-110">Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="0a6c3-111">Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0a6c3-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0a6c3-112">In This Section</span></span>

[<span data-ttu-id="0a6c3-113">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-113">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)  
<span data-ttu-id="0a6c3-114">Proporciona una definición general de serialización, particularmente la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-114">Provides a general definition of serialization, particularly XML serialization.</span></span>

[<span data-ttu-id="0a6c3-115">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="0a6c3-115">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)  
<span data-ttu-id="0a6c3-116">Proporciona las instrucciones paso a paso para serializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-116">Provides step-by-step instructions for serializing an object.</span></span>

[<span data-ttu-id="0a6c3-117">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="0a6c3-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)  
<span data-ttu-id="0a6c3-118">Proporciona las instrucciones paso a paso para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="0a6c3-118">Provides step-by-step instructions for deserializing an object.</span></span>

[<span data-ttu-id="0a6c3-119">Ejemplos de serialización XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-119">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)  
<span data-ttu-id="0a6c3-120">Proporciona ejemplos que muestran los fundamentos de serialización XML.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-120">Provides examples that demonstrate the basics of XML serialization.</span></span>

[<span data-ttu-id="0a6c3-121">Herramienta de definición de esquema XML y serialización XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)  
<span data-ttu-id="0a6c3-122">Describe cómo utilizar la herramienta XML Schema Definition para crear clases que se adhieren a un esquema del lenguaje de definición de esquemas XML (XSD) determinado o que generan un esquema XML de un archivo .dll.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-122">Describes how to use the XML Schema Definition tool to create classes that adhere to a particular XML Schema definition language (XSD) schema, or to generate an XML Schema from a .dll file.</span></span>

[<span data-ttu-id="0a6c3-123">Controlar la serialización XML mediante atributos</span><span class="sxs-lookup"><span data-stu-id="0a6c3-123">Controlling XML Serialization Using Attributes</span></span>](controlling-xml-serialization-using-attributes.md)  
<span data-ttu-id="0a6c3-124">Describe cómo controlar la serialización utilizando los atributos.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-124">Describes how to control serialization by using attributes.</span></span>

[<span data-ttu-id="0a6c3-125">Atributos que controlan la serialización XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-125">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)  
<span data-ttu-id="0a6c3-126">Hace una lista de los atributos que se utilizan para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-126">Lists the attributes that are used to control XML serialization.</span></span>

[<span data-ttu-id="0a6c3-127">Cómo: Especifique un nombre de elemento alternativo para un Stream XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-127">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
<span data-ttu-id="0a6c3-128">Presenta un escenario avanzado que muestra cómo generar varias secuencias XML invalidando la serialización.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-128">Presents an advanced scenario showing how to generate multiple XML streams by overriding the serialization.</span></span>

[<span data-ttu-id="0a6c3-129">Cómo: Controlar la serialización de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="0a6c3-129">How to: Control Serialization of Derived Classes</span></span>](how-to-control-serialization-of-derived-classes.md)  
<span data-ttu-id="0a6c3-130">Ofrece un ejemplo que muestra cómo controlar la serialización de clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-130">Provides an example of how to control the serialization of derived classes.</span></span>

[<span data-ttu-id="0a6c3-131">Cómo: Calificar el elemento XML y nombres de atributo XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-131">How to: Qualify XML Element and XML Attribute Names</span></span>](how-to-qualify-xml-element-and-xml-attribute-names.md)  
<span data-ttu-id="0a6c3-132">Describe cómo definir y controlar la manera en la que los espacios de nombres XML se utilizan en la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-132">Describes how to define and control the way in which XML namespaces are used in the XML stream.</span></span>

[<span data-ttu-id="0a6c3-133">Serialización XML con servicios web XML</span><span class="sxs-lookup"><span data-stu-id="0a6c3-133">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)  
<span data-ttu-id="0a6c3-134">Explica cómo la serialización XML se utiliza en servicios Web XML.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-134">Explains how XML serialization is used in XML Web services.</span></span>

[<span data-ttu-id="0a6c3-135">Cómo: Serializar un objeto como un Stream XML con codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="0a6c3-135">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
<span data-ttu-id="0a6c3-136">Describe cómo utilizar el <xref:System.Xml.Serialization.XmlSerializer> clase para crear secuencias XML SOAP codificadas que se ajustan a la sección 5 del documento de World Wide Web Consortium (W3C) [protocolo de acceso de objeto Simple (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).</span><span class="sxs-lookup"><span data-stu-id="0a6c3-136">Describes how to use the <xref:System.Xml.Serialization.XmlSerializer> class to create encoded SOAP XML streams that conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).</span></span>

[<span data-ttu-id="0a6c3-137">Cómo: Invalidar la serialización XML SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="0a6c3-137">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)  
<span data-ttu-id="0a6c3-138">Describe el proceso para invalidar serialización XML de objetos como mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-138">Describes the process for overriding XML serialization of objects as SOAP messages.</span></span>

[<span data-ttu-id="0a6c3-139">Atributos que controlan la serialización SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="0a6c3-139">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)  
<span data-ttu-id="0a6c3-140">Hace una lista de los atributos que se utilizan para controlar la serialización codificada SOAP.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-140">Lists the attributes that are used to control SOAP-encoded serialization.</span></span>

[<span data-ttu-id="0a6c3-141">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="0a6c3-141">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)  
<span data-ttu-id="0a6c3-142">El elemento de configuración de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-142">The top-level configuration element for controlling XML serialization.</span></span>

[<span data-ttu-id="0a6c3-143">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="0a6c3-143">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)  
<span data-ttu-id="0a6c3-144">Controla el modo de la serialización de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-144">Controls the serialization mode of <xref:System.DateTime> objects.</span></span>

[<span data-ttu-id="0a6c3-145">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="0a6c3-145">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)  
<span data-ttu-id="0a6c3-146">Contiene tipos que usa la clase <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-146">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

[<span data-ttu-id="0a6c3-147">\<Agregar > elemento para \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="0a6c3-147">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)  
<span data-ttu-id="0a6c3-148">Agrega tipos que usa la clase <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-148">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

## <a name="related-sections"></a><span data-ttu-id="0a6c3-149">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0a6c3-149">Related Sections</span></span>

<span data-ttu-id="0a6c3-150">[Servicios Web XML creados con ASP.NET y clientes de servicio Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0a6c3-150">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>  
<span data-ttu-id="0a6c3-151">Proporciona los temas que describen y explican cómo programar los servicios Web XML utilizando ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0a6c3-151">Provides topics that describe and explain how to program XML Web services using ASP.NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a6c3-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a6c3-152">See also</span></span>

- [<span data-ttu-id="0a6c3-153">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="0a6c3-153">Binary Serialization</span></span>](binary-serialization.md)
