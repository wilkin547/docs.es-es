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
ms.openlocfilehash: dcb2ed1703473be582a12f430d2e051d8a420230
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588374"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="10241-102">Serialización de XML y SOAP</span><span class="sxs-lookup"><span data-stu-id="10241-102">XML and SOAP serialization</span></span>

<span data-ttu-id="10241-103">La serialización XML convierte (serializa) los campos públicos y las propiedades de un objeto, así como los parámetros y valores devueltos de los métodos, en una secuencia XML que se ajusta a un documento de lenguaje de definición de esquemas XML (XSD) específico.</span><span class="sxs-lookup"><span data-stu-id="10241-103">XML serialization converts (serializes) the public fields and properties of an object, and the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="10241-104">La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie (en este caso, a XML) para almacenaje y transporte.</span><span class="sxs-lookup"><span data-stu-id="10241-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="10241-105">Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma.</span><span class="sxs-lookup"><span data-stu-id="10241-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="10241-106">Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets.</span><span class="sxs-lookup"><span data-stu-id="10241-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="10241-107">A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.</span><span class="sxs-lookup"><span data-stu-id="10241-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="10241-108">La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP.</span><span class="sxs-lookup"><span data-stu-id="10241-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="10241-109">SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.</span><span class="sxs-lookup"><span data-stu-id="10241-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="10241-110">Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="10241-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="10241-111">Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.</span><span class="sxs-lookup"><span data-stu-id="10241-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="10241-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="10241-112">See also</span></span>

- [<span data-ttu-id="10241-113">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="10241-113">Binary Serialization</span></span>](binary-serialization.md)
- <span data-ttu-id="10241-114">[Servicios Web XML creados con clientes de ASP.NET y servicios Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="10241-114">[XML Web Services created using ASP.NET and XML Web Service clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
