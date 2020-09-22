---
title: Serialización de SOAP y XML
description: En esta introducción se describe la serialización XML, que también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: f7ad7732f929ac3599942c5440b173ea226cca87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544991"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="0e94b-103">Serialización de SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="0e94b-103">XML and SOAP serialization</span></span>

<span data-ttu-id="0e94b-104">La serialización XML convierte (serializa) las propiedades y campos públicos de un objeto y los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="0e94b-104">XML serialization converts (serializes) the public fields and properties of an object, and the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="0e94b-105">La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie (en este caso, a XML) para almacenaje y transporte.</span><span class="sxs-lookup"><span data-stu-id="0e94b-105">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="0e94b-106">Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0e94b-106">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="0e94b-107">Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets.</span><span class="sxs-lookup"><span data-stu-id="0e94b-107">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="0e94b-108">A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.</span><span class="sxs-lookup"><span data-stu-id="0e94b-108">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="0e94b-109">La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP.</span><span class="sxs-lookup"><span data-stu-id="0e94b-109">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="0e94b-110">SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.</span><span class="sxs-lookup"><span data-stu-id="0e94b-110">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="0e94b-111">Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="0e94b-111">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="0e94b-112">Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.</span><span class="sxs-lookup"><span data-stu-id="0e94b-112">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e94b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e94b-113">See also</span></span>

- [<span data-ttu-id="0e94b-114">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="0e94b-114">Binary Serialization</span></span>](binary-serialization.md)
- <span data-ttu-id="0e94b-115">[Servicios Web XML creados con ASP.NET y clientes de servicio Web XML](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0e94b-115">[XML Web Services created using ASP.NET and XML Web Service clients](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
