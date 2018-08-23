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
ms.openlocfilehash: ca3b31c1d60770a6b9db5e92275d9840036ee0b0
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2018
ms.locfileid: "42753913"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="6d0b4-102">Serialización de SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-102">XML and SOAP Serialization</span></span>

<span data-ttu-id="6d0b4-103">La serialización XML convierte (serializa) las propiedades y campos públicos de un objeto o los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="6d0b4-103">XML serialization converts (serializes) the public fields and properties of an object, or the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="6d0b4-104">La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie (en este caso, a XML) para almacenaje y transporte.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="6d0b4-105">Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="6d0b4-106">Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="6d0b4-107">A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="6d0b4-108">La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="6d0b4-109">SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="6d0b4-110">Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="6d0b4-111">Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6d0b4-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6d0b4-112">In This Section</span></span>

[<span data-ttu-id="6d0b4-113">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-113">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)  
<span data-ttu-id="6d0b4-114">Proporciona una definición general de serialización, particularmente la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-114">Provides a general definition of serialization, particularly XML serialization.</span></span>

[<span data-ttu-id="6d0b4-115">Cómo: Serializar un objeto</span><span class="sxs-lookup"><span data-stu-id="6d0b4-115">How to: Serialize an Object</span></span>](how-to-serialize-an-object.md)  
<span data-ttu-id="6d0b4-116">Proporciona las instrucciones paso a paso para serializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-116">Provides step-by-step instructions for serializing an object.</span></span>

[<span data-ttu-id="6d0b4-117">Cómo: Deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="6d0b4-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)  
<span data-ttu-id="6d0b4-118">Proporciona las instrucciones paso a paso para deserializar un objeto</span><span class="sxs-lookup"><span data-stu-id="6d0b4-118">Provides step-by-step instructions for deserializing an object.</span></span>

[<span data-ttu-id="6d0b4-119">Ejemplos de serialización XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-119">Examples of XML Serialization</span></span>](examples-of-xml-serialization.md)  
<span data-ttu-id="6d0b4-120">Proporciona ejemplos que muestran los fundamentos de serialización XML.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-120">Provides examples that demonstrate the basics of XML serialization.</span></span>

[<span data-ttu-id="6d0b4-121">Herramienta de definición de esquema XML y serialización XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)  
<span data-ttu-id="6d0b4-122">Describe cómo utilizar la herramienta XML Schema Definition para crear clases que se adhieren a un esquema del lenguaje de definición de esquemas XML (XSD) determinado o que generan un esquema XML de un archivo .dll.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-122">Describes how to use the XML Schema Definition tool to create classes that adhere to a particular XML Schema definition language (XSD) schema, or to generate an XML Schema from a .dll file.</span></span>

[<span data-ttu-id="6d0b4-123">Controlar la serialización XML mediante atributos</span><span class="sxs-lookup"><span data-stu-id="6d0b4-123">Controlling XML Serialization Using Attributes</span></span>](controlling-xml-serialization-using-attributes.md)  
<span data-ttu-id="6d0b4-124">Describe cómo controlar la serialización utilizando los atributos.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-124">Describes how to control serialization by using attributes.</span></span>

[<span data-ttu-id="6d0b4-125">Atributos que controlan la serialización XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-125">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)  
<span data-ttu-id="6d0b4-126">Hace una lista de los atributos que se utilizan para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-126">Lists the attributes that are used to control XML serialization.</span></span>

[<span data-ttu-id="6d0b4-127">Cómo: Especificar un nombre de elemento alternativo para una secuencia XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-127">How to: Specify an Alternate Element Name for an XML Stream</span></span>](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
<span data-ttu-id="6d0b4-128">Presenta un escenario avanzado que muestra cómo generar varias secuencias XML invalidando la serialización.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-128">Presents an advanced scenario showing how to generate multiple XML streams by overriding the serialization.</span></span>

[<span data-ttu-id="6d0b4-129">Cómo: Controlar la serialización de clases derivadas</span><span class="sxs-lookup"><span data-stu-id="6d0b4-129">How to: Control Serialization of Derived Classes</span></span>](how-to-control-serialization-of-derived-classes.md)  
<span data-ttu-id="6d0b4-130">Ofrece un ejemplo que muestra cómo controlar la serialización de clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-130">Provides an example of how to control the serialization of derived classes.</span></span>

[<span data-ttu-id="6d0b4-131">Cómo: Calificar el elemento XML y los nombres del atributo XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-131">How to: Qualify XML Element and XML Attribute Names</span></span>](how-to-qualify-xml-element-and-xml-attribute-names.md)  
<span data-ttu-id="6d0b4-132">Describe cómo definir y controlar la manera en la que los espacios de nombres XML se utilizan en la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-132">Describes how to define and control the way in which XML namespaces are used in the XML stream.</span></span>

[<span data-ttu-id="6d0b4-133">Serialización XML con servicios web XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-133">XML Serialization with XML Web Services</span></span>](xml-serialization-with-xml-web-services.md)  
<span data-ttu-id="6d0b4-134">Explica cómo la serialización XML se utiliza en servicios Web XML.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-134">Explains how XML serialization is used in XML Web services.</span></span>

[<span data-ttu-id="6d0b4-135">Cómo: Serializar un objeto como secuencia XML con codificación SOAP</span><span class="sxs-lookup"><span data-stu-id="6d0b4-135">How to: Serialize an Object as a SOAP-Encoded XML Stream</span></span>](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
<span data-ttu-id="6d0b4-136">Describe cómo utilizar el <xref:System.Xml.Serialization.XmlSerializer> clase para crear secuencias XML SOAP codificadas que se ajustan a la sección 5 del documento de World Wide Web Consortium (W3C) [protocolo de acceso de objeto Simple (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).</span><span class="sxs-lookup"><span data-stu-id="6d0b4-136">Describes how to use the <xref:System.Xml.Serialization.XmlSerializer> class to create encoded SOAP XML streams that conform to section 5 of the World Wide Web Consortium (W3C) document titled [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/).</span></span>

[<span data-ttu-id="6d0b4-137">Cómo: Invalidar la serialización XML SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="6d0b4-137">How to: Override Encoded SOAP XML Serialization</span></span>](how-to-override-encoded-soap-xml-serialization.md)  
<span data-ttu-id="6d0b4-138">Describe el proceso para invalidar serialización XML de objetos como mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-138">Describes the process for overriding XML serialization of objects as SOAP messages.</span></span>

[<span data-ttu-id="6d0b4-139">Atributos que controlan la serialización SOAP codificada</span><span class="sxs-lookup"><span data-stu-id="6d0b4-139">Attributes That Control Encoded SOAP Serialization</span></span>](attributes-that-control-encoded-soap-serialization.md)  
<span data-ttu-id="6d0b4-140">Hace una lista de los atributos que se utilizan para controlar la serialización codificada SOAP.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-140">Lists the attributes that are used to control SOAP-encoded serialization.</span></span>

[<span data-ttu-id="6d0b4-141">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="6d0b4-141">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)  
<span data-ttu-id="6d0b4-142">El elemento de configuración de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-142">The top-level configuration element for controlling XML serialization.</span></span>

[<span data-ttu-id="6d0b4-143">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="6d0b4-143">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)  
<span data-ttu-id="6d0b4-144">Controla el modo de la serialización de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-144">Controls the serialization mode of <xref:System.DateTime> objects.</span></span>

[<span data-ttu-id="6d0b4-145">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6d0b4-145">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)  
<span data-ttu-id="6d0b4-146">Contiene tipos que usa la clase <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-146">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

[<span data-ttu-id="6d0b4-147">\<Agregar > elemento para \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="6d0b4-147">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)  
<span data-ttu-id="6d0b4-148">Agrega tipos que usa la clase <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-148">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> class.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6d0b4-149">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6d0b4-149">Related Sections</span></span>

[<span data-ttu-id="6d0b4-150">Tecnologías de desarrollo avanzadas</span><span class="sxs-lookup"><span data-stu-id="6d0b4-150">Advanced Development Technologies</span></span>](https://msdn.microsoft.com/library/c4a7e341-f0c6-4df4-a74f-223387ac6e4e)  
<span data-ttu-id="6d0b4-151">Proporciona vínculos para más información sobre tareas y técnicas de desarrollo sofisticadas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-151">Provides links to more information on sophisticated development tasks and techniques in the .NET Framework.</span></span>

[<span data-ttu-id="6d0b4-152">Servicios Web XML creados con ASP.NET y clientes de servicio Web XML</span><span class="sxs-lookup"><span data-stu-id="6d0b4-152">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c)  
<span data-ttu-id="6d0b4-153">Proporciona los temas que describen y explican cómo programar los servicios Web XML utilizando ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6d0b4-153">Provides topics that describe and explain how to program XML Web services using ASP.NET.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d0b4-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d0b4-154">See Also</span></span>

[<span data-ttu-id="6d0b4-155">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="6d0b4-155">Binary Serialization</span></span>](binary-serialization.md)  